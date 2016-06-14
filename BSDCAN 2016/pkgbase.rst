.. _pkg base:

PKG Base
========

etc is the biggest issue to pkg base currently

rc.firewall might need a different configuration

Each time we can avoid a merge, pkgbase will be improved

Anything under /etc FreeBSD attempts to merge

Mergeability exists, but resolvability doesn't yet.

FreeBSD already has interactive resolve.

Use etc/update instead of an install script
The config file has special flags

freebsd sources are built from a different branch which can result in ID tag conflicts
If someone does build world/install world

install world might have to be in the base system, resulting in pkg being moved into the base system
if so, ports logic might need to be excluded
pkg is already a floating target
running install world from base could result in errors from packages in ports. 

We need backwards compatibility addressed
compatability is easy to do ion revisioin tests
bugs exist which need to be addressed

PCBSD includes package base as standard?

2 reason somethin not in pkgbase
mk files miss something
if smthng instlled wthout install command

install world should come from the staging directly to prevent accidental building
flow should be: stage - install - post install cleaning mechanism

kernel incoherent needs to be moved to post-install world.
the hints file is the reference for some of the build scripts
install file should not make any new files, just move existing files around.
doing an install kernel should not be part of install world
dirtapps build stages everything in a directory, with no install world mechanism
cluster builds the staging directory and just copies everything via target
cluster does compat libraries first.
cluster intentionally replaces every file
stageworld creates one metalog and in a roundabout manner does what is needed for pkg 
stageworld could be a hidden part of the process
do we have room for an inbetween mechanism which maintains a local copy of what is being installed. a layer on top of package
do you generate binary diffs for changed files? yes, it is incremental
the challenge with deltas for packages
if lib archive threads compression several error will be created. 
you cannot do diffs of compressed packages, a pkg must be uncompressed, run the diff, then recompressed?
when doing an update the system needs to be sure it has the correct files.
what about signing the pakcages. but its all compressed first and too inefficient to uncompress.
a distribution mechanism where the local files are inspected first, then only the updated (diff) files are then downloaded.
biggest package in base in kernel (35mb)
making packages smaller makes everything easier. bandwidth efficiency is still critical for a large number of people who are still on dialup.
freebsd update was not designed with updating the source tree constantly in mind
freebsd update uses less bandwidth than cvs update.
we shouldn't go down the route were packages are the only way for a user to update their system.
issue: how items are signed offline
 - there are many problems that are difficult to work through
a kernel pkg without any modules and one pkg with all the modules
can you combine the pkg updates with something like freebsd update?
what about a p0 p1 package that brings updates to the binary files for quick updates?
binary patches don't provide any feedback at all. there would have to be an additional mechanism to ensure the binaries have been patched correctly.
any changes to pkg will have to be flexible enough to handle any churn or a wide variety of user activity.
diffs should be applied to packages and not the other way round. 
what about an artificial limiter to throttle?
Issue: trickle updates announce to the world that the updating system is out of date and vulnerable to exploit.
people really need to help with pkg running test, reporting bugs,
is this same problem with the vital flag? a new update was released a couple days ago which should address vital flags, but needs additional testing.
freebsd runtime package is flagged vital, so it should never be uninstalled (unless the flag is removed, during an up/downgrade for example)
is the capital F flag used for anything?
provide, requires, and supercedes are useful functions, but very dangerous. 
one way to help avoid errors is to strictly maintain unique package names
if a package disappears from a remote repository, regression testing becomes important
adding replacement tags becomes dangerous as files will later become dependant upon each other, resulting in pkg errors as updates try to replace files that were previously unneeded and removed.
one issue is where a library has the same number in base and ports, which creates reference errors.
Getting many errors about missing libraries has something to do with the staging directory.
is there a plan for versioning? there is a current issue where stable branch gets redownloaded completely for updates to smaller areas.
security fixes 