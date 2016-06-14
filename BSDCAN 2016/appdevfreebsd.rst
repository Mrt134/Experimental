.. _appdev freebsd:

Application Development in FreeBSD
==================================

(using modern tooling)

The cloud world is lagging behind the rest of the computing world in adopting (good) new tools.

using packer to create a script 

Problems with FreeBSD

Stability
 - like uptime
 - max lifetimes
Debuggable
Knowledgeable Admins
 - Doc Project
Performance
 - enomem
 - fixed userland kernel
Secure
Manageable
 - In place upgrades are simple
Embeddable
Pride

This has led to the creation of the wrong set of KPIs for users
Solution: Cloud KPIs
 - reduce the effort required to spin up a new instance
 - documentation
 
Modern workflow
1. spin up a vm
2. create golden image per Application
3. upload golden image
4. scale g i in production

with the exception of few configurations, golden image and user install should be the same

Vagrant
vagrant allows a command line interaction with virtualized image
vagrant allows VMs to be largely disposable (the goal)

vagrant, packer, into production with terraform or nomad

VNC has a very frustrating element in that wait commands aren't really useful
using packer for script(s) files allows for a high degree of repeatability
can you mount and change .isos before they are booted? No
The goal is to download a couple utilities, the .iso then spin up a vm or install without any additional bootstrapping or tweaking.
