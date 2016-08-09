.. handbook
Minimum Hardware Requirements
The hardware requirements to install FreeBSD vary by architecture. Hardware architectures and devices supported by a FreeBSD release are listed on the Release Information page of the FreeBSD web site (http://www.FreeBSD.org/releases/index.html). The FreeBSD download page also has recommendations for choosing the right image for your architecture (https://www.freebsd.org/where.html)

A FreeBSD installation will require 64 MB of RAM and 1.5 GB of free hard drive space at minimum. However, this is not recommended as almost no free space will be left on the system. RAM requirements will depend on usage, with some customized FreeBSD systems using as little as 128 MB of RAM while general desktop systems are recommended to have 4 GB of RAM.

The processor requirements for each architecture can be summarized as follows:

amd64
This is the most common desktop and laptop processor, used in most modern systems. This architecture can also be called x86-64, and is used by both Intel® and AMD. Examples of amd64 compatible processsors include: AMD Athlon™64, AMD Opteron™, multi-core Intel® Xeon™, and Intel® Core™ 2 and later processors.

i386
Older, home based systems will generally use this 32-bit x86 architecture.

Almost all i386-compatible processors with a floating point unit are supported. All Intel® processors 486 or higher are supported.

FreeBSD will take advantage of Physical Address Extensions (PAE) support on CPUs with this feature. A kernel with the PAE feature enabled will detect memory above 4 GB and allow it to be used by the system. However, using PAE places constraints on device drivers and other features of FreeBSD; refer to pae(4) for details.

ia64
Currently supported processors are the Itanium® and the Itanium® 2. Supported chipsets include the HP zx1, Intel® 460GX, and Intel® E8870. Both Uniprocessor (UP) and Symmetric Multi-processor (SMP) configurations are supported.

pc98
NEC PC-9801/9821 series with almost all i386-compatible processors, including 80486, Pentium®, Pentium® Pro, and Pentium® II, are all supported. All i386-compatible processors by AMD, Cyrix, IBM, and IDT are also supported. EPSON PC-386/486/586 series, which are compatible with NEC PC-9801 series, are supported. The NEC FC-9801/9821 and NEC SV-98 series should be supported.

High-resolution mode is not supported. NEC PC-98XA/XL/RL/XL^2, and NEC PC-H98 series are supported in normal (PC-9801 compatible) mode only. The SMP-related features of FreeBSD are not supported. The New Extend Standard Architecture (NESA) bus used in the PC-H98, SV-H98, and FC-H98 series, is not supported.

powerpc
All New World ROM Apple® Mac® systems with built-in USB are supported. SMP is supported on machines with multiple CPUs. However, a 32-bit kernel can only use the first 2 GB of RAM.

sparc64
Systems supported by FreeBSD/sparc64 are listed at the FreeBSD/sparc64 Project (http://www.freebsd.org/platforms/sparc.html).

SMP is supported on all systems with more than 1 processor and a dedicated disk. At this time, it is not possible to share a sparc64 disk with another operating system.

.. website

Download FreeBSD

Choosing an Architecture

Modern PCs use the amd64 architecture, including those with Intel® branded processors. Computers with more than 3 GB of memory should use amd64. If the computer is an older, 32-bit only model, use i386. For embedded devices and single-board computers (SBC) such as the Raspberry Pi, Beagle Bone Black, Panda Board, and Zed Board, use the armv6 SD card image which supports ARMv6 and ARMv7 processors.

Choosing an Image

The FreeBSD installer can be downloaded in a number of different formats including CD (disc1), DVD (dvd1), and Network Install (bootonly) sized ISO Disc Images, as well as regular and mini USB memory stick images. Later versions of FreeBSD are also offered as prebuilt expandable Virtual Machine images, and as SD Cards for embedded platforms.