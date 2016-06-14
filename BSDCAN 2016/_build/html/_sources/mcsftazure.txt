.. _mcsft azure:

Microsoft Azure Presentation
============================

Microsoft has been moving into the opensource arena with Azure.
Contributes to freebsd generally through openssh.

Why?

Common base OS for appliances.

- Stable mature and performant S
- Permissive BSD licensing attractive for Appliance vendors
 
Appliances are going virtual.

- Virtual appliances following the trend of server density
- Startup VA vendors are fogoing physical all together
 
Hyper-V and Azure suport.

- Microsoft does have on staff a committer to the FreeBSD kernel.

Timeline

2012 - citrix, hyper V
2014 - hyper V support for FreeBSD 10.0+
2015 - Azure Marketplace lunached by Gemalto and Array Networks

optimizing networking performance is a primary goal for mcsft.
increasing partnerships
Azure Marketplace will provide a VM image of FreeBSD 10.3 available (stand-alone package - microsoft provides support)

Most have heard of Azure, few have used it.

Microsoft desires to lead in cloud tech providers.
Azure: 57% of Fortune 500 companies use Azure, growing profitability.

Azure has :

- Hyper-scale: Massive data servers (100+ datacenters globally) providing global network and storage potential
- Enterprise grade: Reliability and recovery high standards.
- Hybrid: Azure allows companies to have on-site data stacks AND cloud services available, hybridizing their storage solution as necessary.
- Open & Flexible: 30% of microsoft vms are open source. Microsoft is changing its corporate attitude toward open source

Azure marketplace:

- Online store for apps
- certified 3rd party
- NIX and windows based
- Easy to deploy
 
Demo: getting a freebsd vm started from azure marketplace
:menuselection:`microsoft azure --> partners --> azure marketplace -> search for FreeBSD 10.3 --> click create Virtual Machine`.
The marketplace then moves through a step by step process to create the virtual machine. It is possible to add extensions to a virtual machine
Press a button to login to the virtual machine and bring up the command prompt/initialization screen.
Azure is a subscription based service, requiring a registration and credit card information.

Publishers:

- Flow
- Apply to microsoft, onboarding, certification, publishing, marketing
- Microsoft provides testing to ensure solution is compatible with azure

BSD solutions in azure marketplace:
azure vapv -byol, pfsense, safenet, netscaler vpx, stormshield net security

.. _pfsensedemo:

Demo: Netgate pfSense: Chris Buechler
-------------------------------------

Web GUI-managed freeBSD- based firewall distro
Began in 2004 and is now (2016) the most widely-used OSS firewall distribution.
current release: 2.3.1 with freebsd 10.3 base
Azure image launched in mid-May

Public Cloud Use Cases
VPN (virtual private network)

- Site to site
- mobile users
- service providers offering an application (which lives in a cloud, provider creates an open vpn for users to access the application)

routing, NAT, firewall

-azure allows configuration, but some visibility is restricted 
- azure doesn't support ipv6 yet
- some companies like to bundle all their ips on one vpn to save on ip costs

testing, simulation

- azure offers some options for testing by adding limiters, enabling some throttling or packet loss options.

Public and Private transactions handled by Azure
Demo of pfSense
Creating VPN, 

Thanks microsoft.
QA

Question: Does pfSense support IPv6?
Answer: IPV6 support is in pfSense, but not its current Azure iteration.

.. _microsoftagain:

Microsoft Continued
-------------------

How to enable your FreeBSD to Azure:

1. Get FreeBSD running well on Hyper-V
2. Install Azure Agent
3. Configure your VM for Azure
4. Upload your .VHD

How Operating Syss run on Hyper-V
The operating system **must** be x86/x64 for proper functionality. Also, integration services should be present (if not, then emulation may work, but functionality will be limited).
Integration Service for FreeBSD (BIS)

Hyper-V presents synthetic devices to the guest OS

- Synthetic Devices seen by the guest OS are the same, regardless of the real hardware hyper v

Changes to FreeBSD

- driver source code is in sys/dev/hyperv
- include/hyperv.h
- netvsc
- stordisengage
- storvsc
- utilities
- vmbus
- other minimal changes to the freebsd kernel

Support issues can be sent to microsoft or FreeBSD
HyperV and Azure issues will be supported by Microsoft

hyper-v is on github as a public repository.
A deep dive session will be available at the end of the conference to demonstrate or provide net performace improvements.
hyperv server has a free sku through http://www.microsoft.com

.. _azure agent:

Azure Agent
-----------

Provisioning (during VM creation)
Running 
De-provisioning

Azure agent:
The open source repository is available on github.
Branch 2.0 is meant for freebsd 10 and 10.1 installations.
Branch 2.1 for later/newest versions of FreeBSD.
Configure your VM for Azure:

- enable dhcp
- enable ssh
- set up serial console
- install sudo

Upload your .vhd

1. Azure subscription required, Azure does have powrshell tools
2. Create Azure storage acccount
3. Prepare the cann to mic az
4. Upload the .vhd file
5. Create a vm with uploaded vhd

Caveats
vm extensions in Azure do not all work with FreeBSD VMs: varied nature of freebsd distros va vendors ship
(Example: Diagnostics are completly nonfunctional)
If bringing freebsd va into Azure, must be whitelisted.
Conclusion: azure + open source= increasing profit margin for partners.