.. _zfs:


ZFS is copy on write: all writes allocate
Variable block size
512 b up to 16 mb
Compression
  any multiple of 512 is possible
32,768 allocation sizes
(default max 128kb on 4k device => 32 sizes

ZFS allocate
 Write syscall (or via NFS or iSCSI)
 record dirty data in memory
 *asynchronous rates
 
Periodically write all dirty data to disk
 every 1-10 seconds
 spa_sync aka TXG flush
 
spa_sync

1. vdev
  a. assume vdevs have inependent perf
  b. round robin among vdevs
  c. allocate same amount (512kb) to each - exception: less free space -> less allocation
2. metaslab
  a. assume sequential writes are better - try to stick with same metaslab(s)
  b. Start with metaslab with most fragmentation-weighted free space
  c. Stick with it until it's >70% fragmentation - average free chunk size <32KB
3. offset

Each metaslab uses a data structure called a spacemap, which has an on-disk free chunk size histogram
new metaslab selection begins with the one with the largest and the most free chunks.

Allocation problem stemming from devices in the pool having different write performance.
The solution has been to have a dynamic allocation where vdev holds 100 allocations across the storage solutions and issues write commands based on write speed, fragmentation, size of free chunks, etc.
The end result has been up to double better write performance.

On-disk structures
Each vdev divided into ~200 metaslabs - each metaslab tracks free space in on-disk spacemap.
spacemap is on-disk log of allocations & frees
each spacemap stored in object in MOS 
periodically condense each spacemap - write out as all ALLOC records

Recording allocations on-disk
To allocate, must know exactly what is allocatable
Must load spacemap from disk into range tree
range tree is in memory structure
 - balanced binary tree of free segments, sorted by offset
 - 2nd tree sorted by length
A metaslab is 1-1 with the spacemap, which is 1-1 with the range tree.
Any metaslab can be frozen during an allocation

Writing Spacemaps
each spa_sync() each metaslab tracks
 - allocations
 - frees
at end of TXG
 - append alloc & free range_trees to space_map
 - clear range_trees
dynamic behavior
 - usually freeing blocks in most metaslabs
 - usually appending to most metaslabs
 - ~600 i/os per vdev per txg (1 data + 2 indirect)

Problem: Reading spacemap is slow
because space_map_blksz=4kb
because we append to every spacemap every txg
 - space_map_blksz=128kb => write 25MB/vdev/txg
 - 10 vdevs =>at least 6% bandwidth overhead

 
Problem: loaded spacemap uses lots of memory
metaslab covers huge range (50gb on 10TB vdev)
range tree uses up to 320 MB RAM (on 10TB vdev)

Solutions
different # metaslabs per device?
different space map blocksize?
each solution has a speedup and slowdown effect, resulting in no improvement

Problem: Append to most spacemaps most TXGs
 - ~600 i/o's per vdev per txg!

Found Solution:
don't flush every modified metaslab every txg
keep changes in memory until flushed
 - range tree of unflushed allocs
 - range tree of unflushed frees
 - non-overlapping limits size and don't need order info
 - to load metaslab
  - read spacemap from disk
  - apply unflushed allocs & frees
flush ~1 metaslab per TXG
  - it will have lots of changes
  - efficiency: each TXG append lots of data to few spacemaps
What if we crash
 - can't lose unflushd allocs/frees
sol. write all metaslabs' changes in one spacemap
     after unclean shutdown, read vdev's spacemap and reconstruct each metaslab's unflushed allocs/frees
     
     how many metaslabs to flush each txg? 1 at least is required. Also limit reconstruction time by limiting the size of vdev's spacemap

Results
 this scheme solves metaslab issues
 overhead will be drastically reduced, but real world workload performance will likely not be as much
 
 Delphix is sponsoring an openZFS conference & hackathon in san fran.