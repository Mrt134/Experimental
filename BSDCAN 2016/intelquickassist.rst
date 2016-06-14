.. _intel quickassist:

Intel QuickAssist (Devsummit session 2 1106am) by Fiona Trahe
=============================================================

Intel quickasist tech overview

- Bulk Crypto: High speed encrypt/decrypt
- Public Key Crypto: Heavily map intensive/cpu cycles
- Compression: lossless data compression for data in flight and rest

Form factors

- Chipsets
- PCI express Plugin Card
- SoC - Connects to CPU via on chip interconnect
- Tech is relatively mature with continued optimization

Potential Applications

  - Cloud
      
      - Secure Networking
      - Efficient VM Migration
      - Databases
  - Networking
      
      -Secure Routing
      -Web Proxy
      -WAN Optimize
      -Wireless infrastructure
      
  - Big Data
    
      - Analytics (APACHE Hadoop)
      
  - Storage
    
      - Data integrity
      
- Terminology:

  I QA T integrates hardware acceleration of compute intensive workloads (specifically, crypto and compression on intel arch. platforms
  Crypto primitives supported:
  
    - Compression and decompression (static and dynamic)
    - algorithms: Deflate (LZ77 plus Huffman coding with gzip or zlib header)
    - stateful and stateless compression and decompression (stateless recommended) 
    - symmetric ciphers
    - message diges hash
    - algorithm chaining and autheniticated encryption
    - public key crypto

Operating Systems ,hypervisor, and frameworks: FreeBSD, Linux, other os' not publically available
Applications
  Web Server, engineX, mysql, dropsdb
Services and Engines
  Each I QA T device offers up to four services
    -PKE
    -SYM
    -RNG
    -DA
  Each service has multiple engines with accelerators and threads
  DMA writes to the DRAM are also cached in the LLC per the Intel data direct/io tech
  Overview of Service Engine:
  Dram CPU and PCIE
  data enters the chip through channels/rings/qpips , etc. (in DRAM)
  request for encrypted data goes to DRAM, which writes to a PCIe endpoint
  most of the work is done in the DRAM, but the PCIe conducts the compression
  most work is DRAM read/writes
  This results in relatively quick compression/encryption speeds.
  PCI bandwith is (one) limiting factor to encrypt speeds
intel quickasist freebsd port
   I QA T driver on FreeSD 10.x (direct model, out of tree)
     initial port in q2 2016
  issues with porting
    common code base
    for all operating systems - FreeBSD, etc.
    Multiple Repos
      common Repos (6 or 7)
      individual platform repos
      single mainline branch development - changes for one platform applies to all
    Scripts/macros/compile time flags to generate release packages for each os
    in-tree/out-of-tree/direct/indirect
    *Found FreeBSD to be much more flexible, leading to faster development*
intel quickasist data plane development kit (DPDK)
  current cryptodev implementation
    supports software and hardware symmetric crypto
      one top shop for best of intel crypto
      all harware implementations also have software implementations
  supports standard ipsec aes and sha algorithms as well as snow3g Wireless algorithms
  upstreaming to dpdk.org with an ipsec sample Applicationsuses the stock kernal driver to init
  can add new accel device types to the arch
device exposure
DPDK Crypto APIs
  crypto device management apis
  crypto stats and capabilities apis
  symmetriccipher/hash algorithm definitions
  session management apis
    number of sessions is user defined
  operation management apis
  burst apis
    group encryption requests together and for simple transmission to the hardware
qa: dpdk is company and os (mostly) agnostic. (any x86 cpu)
