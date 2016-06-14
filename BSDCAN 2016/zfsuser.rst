.. _zfs user meeting:

ZFS user meeting
================

Newer features (BSDCAN 2016)

- compressed arc
- allocation improvements
- compressed send/receive
- ABD
- redacted send/receive
- **device removal**
- channel programs
- written#bookmark property, fast send estimate from bookmark
- spa load/import diagnosability improvements
- eager zero
- zfs encryption(!)

compressed send/receive (physicial representation s/r)
redacted send/receive - feature for security distribution - creates a clone of a database and masks sensitive data, then uploading the masked file to the server storage

non-ZFS stuff from Delphix (not upstream yet)

- dtrace syntactic sugor (if/else, entry ->, callers[])
- TCP per-connection statistics (connstat)
- TCP high-res RTT (connstat)

cache/log devices can be removed with zpool remove
openzfs runs on top of virtualized storage