.. _helloworldpresent:

Everything you ever wanted to know about "hello, world," but were afraid to ask. Brooks Davis 6/10/16
=====================================================================================================

Hello world used to be simplest C program possible, but it is far more complicated than it appears.

in minimal C hello world has a stripped binary over 550K in size.

c compiles massive data strings to process all the data.

https://people.freebsd.org/~brooks/talks/bsdcan2016-helloworld

execve takes an existing process and replaces with the content of the program you want to run.

1. allocate memory
2. copy program path

kern_execve()

1. namei() resolve path
2. exec_check_permissions()
3. exec map first page

exec_elf64_imgact()
A. exec_new_vmspace()

1. pmap_remove_pages()
2. vm_map_stack()

B. elf_load_section() .txt
C. elf_load_section() .data

exec_copyout_strings()
exec_setregs() - sets internal register to return to beginning with correct arguments

Stack mapped
program mapped
call the startup function

bottom of the stack is the argc (argument count)
_start() spends most (90%+) cycles in malloc()
_init_tls() - still spends most of its time in malloc
 - finds the elf auxargs vector
 - use that to find the program header
 - use those to find the pt_tls section (initial values)
 - call _libc_allocate_tls()
  - allocates space
  - copies initial values
(TLS - thread local storage)
  - TLS pointer is set on perthread basis
CherryBSD is a memory safe flavor of FreeBSD (for testing purposes)
main()
  _get_locale()
vfprintf does all the actual work of printing a strings
the function has to allocate an array to 
vfprintf assembles a buffer and flushes those item out of the array in one motion
write system call goes at the end with _sprint()
_flush()
exit()
- call destructors registers through addexit function
- does deallocation and cleanup

Dynamic Libraries
-----------------

has quite a lot of overhead
runtime linker relocates itself first, then loads and relocates libc. The libc relocate tries for the same position as the linker
printf() starts by looking for the v1.0 of the printf symbol
once the symbol is found, it returns and configures the table with the proper symbol.

Feedback requested
http://bit.ly/bsdcan16-hellowworld

exec copy out take the items copied into, and moves them out, following a specific process

Q: what is nps_strings?
A: pointer to one or more argument strings and the environment; primarily used to call set block tile to change the name of the program. 
Q: what are you kicking off the stack in CherryBSD
A: everything; none of these items have any relation to the other build stack. Don't really want them to be accessible globally.
Q: anything folding back from CherryBSD useful for non-specialized systems?
A: not really.
Q: in the context of a new program. what does the flush if I leave a new line off
A: the cleanup routine
Q: would a flush occur with nothing in the buffer
A: yes