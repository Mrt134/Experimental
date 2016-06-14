.. _freebsd11:

FreeBSD 11 and 12
=================

* PCIe HotPlug
* iwm(4)
* Updated KMS
* Linux64 (also in 10.3)
* RISC-V
* Clang/LLDB/libc++ update to 3.8
* iSER/ cxbei
* EFI, ZFS, GELI boot
* AIO network (zerocopy TCP on cxgbe)
* Debug symbols
* sendfile() rewrite
* reroot
* FAST_DEPEND
* truss refacoring
* ioat(4) / ntb(4)
* arm64
* devctl (also in 10.3
* vt(4) as default
* Coorectly enumerate primes between 4295098369 and 3825123056546413050
* zfsd
* sesutil / mpsutil (10.3)
* Dumps to AF-4Kn
* CAM I/O scheduler
* getppid() doesn't report debugger
* autofs (10.1) (backported into 10)
* CAM devd events
* ypldap (LDAP inside NIS)
* Locale rework 
* PQ_LAUNDRY 

The list is very incomplete. Additional contributions:

* Blacklistd
* transport TCP is now pluggable
* Coverity fixes
* Test suite updates
* Casper (casperd -> libcasper migration)
* libnv
* SR-I0V
* ixl
* mlx5
* iflib
* byhyve UEFI + G0P
* Linux KPI
* libcuse (userspace character devices)
* RSS Updates
* Jails IPC
* RCTL disk limiting
* Hard Float ABI for ARM 
* pthread robust mutexes
* pthread process shared mutexes
* NPT + NAT64 in IPFW
* SMR support
* rman resource size upgrade (better PAE resource handling)
* Native ifnet on WLAN
* mandoc
* 802.11 cleanup
* kernel modules tagged with PNPinfo
* DTrace updates
* Newer powerpc core support (PMC on this)
* utrace in truss
* x2APIC, interrupts remapping on x86, potential support for > 254 CPUs
* OOM rework
* more fine grained locking for AMD64 pmap
* PCID on AMD64 rewritten and enabled by default
* packaging base
* ARMv6 + ARM64 Packages
* 100G I/O Scaling
* More NUMA
* compressed disk improvements
* LRO improvements
* Timer fixes
* Async Drain
* NTP updates
* PPS fixes
* fewer GPL
* ELF toolchain bits
* xToolchain support
* Allwinner CPU/SoC support
* INTRng
* VIMAGE fixes
* Clock framework
* more fine grained locking for AMD64 pmap
* PCID on AMD64 rewritten and enabled by default ("PCID works")
* Fortuna PRNG
* Hyper-V
* Xen DOM0
* SIFTR/TCP Debug reimplemented in DTrace
* DTrace MBUF provider
* IPSEC on by default
* NETMAP on by default
* Additional IPFilter DTrace probes
* ARM superpages
* Make Analyze (Clang static analyzer) (only userland for now)
* Clang profiling / Compiler RT
* DragonFly Mail Agent (DMA)
* TCP debug packet cache
* Reduced library overlinking in the base system
* Improved ACPI C-states support
* review of atomics(9) use, manpage updates
* ZFS resumable send
* ZFS TRIM
* ZFS hashes (SHA512, Skein)
* CTL Improvements (CTL HA)
* Killed IA64
* Killed ReiserFS
* Installworld errors on newer source files
* review of atomics(9) use, manpage updates

**Still Needed in 11**

arm64 installer - Doesn't know how to use EFI etc. in the partition editor.

.. _freebsd12:

FreeBSD 12 Goals
================

- GPL Free in 12.0
- Kill GCC 4.2.1
- kill binutils
- init replacement
- rc.d replacement
- service management framework
- machine readable tooling (libxo output, libucl input)
- CPU scaling

  - NUMA
  - More CPUS
  
- libnv interchange
- libucl for more config files (newsyslog.conf, login.conf, etc) <--- standard configuration format across the OS? - - Yes. Human and Machine editable
- login cap database lookup improvements
- Improvements to libc .db support
- librification (libifconfig https://github.com/Savagedlight/libifconfig)
- 64bit inodes (max mount path len)
- X32, i386 T64 (32bit time_t)
- Power Management
- Tamper resistent boot
- Suspend to disk
- SDIO (SD interface for wi-fi, bluetooth
- Structured syslog
- UEFI boot manager (EFI variables, runtime services)
- 64 bit timet on PPC
- ntimed (replace NTPd)
- **Kill Giant**
- RNG improvements
- Watchdog improvements
- 3d Crosspoint, NVDIMM, etc.
- persistent memory file system
- framework for a log of errors/ Fault manager
- Cross build support (linux/mac clusters)
- Portable libKDM
- Generic ARMv7 kernel
- Tier 1 status for arm 32/64 (v6)
- VOP dealloc
- Sparse file support (Sparcification, hole punching)

newbus fine-grained locking
PQ_LAUNDRY (11.1 :)
vm_page_free_queue_mtx problem
libthr2 (inlined pthread locks)
ASLR and other hardening implementations nonsense
ifunc-like MD hooks, refreshed after CPU firmware update
pre-boot CPU firmware update

Virtual memory compression - "ZRAM"
User-configurable (run-time) USB or other quirks
Pluggable schedulers
Byte Queue Limits (BQL) for NIC TX paths 
Replace OpenSSL with LibreSSL

Internet supplied ideas
-----------------------

via twitter @jmcwhatever)

  Support for SDIO wireless devices found on many ARM boards
  Faster transfer modes for SD cards (UHS-I) and eMMC (HS200/HS400)
  64-bit Allwinner support
  SDHCI scatter-gather DMA (ADMA2)
  Multi cluster support on armv6

Latest PF from OpenBSD - (via twitter @pauldokas)

via twitter @FUNTOWNE

  AC Wireless support - Edit: binary blobs are OK in the nearterm
  ext4 write support with journaling. Help with migrations :)

via twitter @bsdlme

  Replace ntpd and sendmail

More blackboards
libucl for more config files (newsyslog.conf, login.conf, etc) <--- standard configuration format across the OS? Yes. Human and Machine editable
login cap database lookup improvements
Improvements to libc .db support
More gig

Haves for FreeBSD 12
--------------------

- rc.d replacement (initially built on launchd)
- TLS sendfile [rrs]
- network.subr v6 dhclient enhancements
- libunwind (from llvm instead of pcc) [emaste]
- ZFS compressed ARC [gwilson]
- ZFS encryption [openzfs]
- ZFS device removal [mahrens]
- ino64 compat [benno]
- registration of cryptographic ciphers dynamically (opencrypto) [dwm]
- dtrace CPC [gavide]
- Energy aware scheduler [avm]
- Kernel debugging and testing framework (ddb shell) [tt]
- SMT disable tunable (boot loader)
- IPV6 improvements to bsnmpd [ngie]
- bsnmp trap fixes [ngie]
- intel DRM (video) 4.6 drivers [scottl]
- Kernel core file performance improvements [wca]
- TCP/UDP per-socket rate limit support
- Virtualization PV PCI Interrupts
- LIT compiter for bpf on armv7
- encrypted kernel crash dumps

Wants for FreeBSD 12
--------------------

- SG X (intel provided security solution)
- Host aware SMR file system
- One true viable laptop
- Open Stack
- CEPH
- MDB features
- nand device support
- nandfs
- stem cell images (the ability to have a freebsd image that doesn't have a base installer) (Sean Chitenden with Hashcorp)
- DHCP v6 client in base
  