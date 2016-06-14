.. _freefromgoogle:

Dodging Raindrops: Escaping the Public Cloud
============================================

A user story of De-Google-ication using FreeBSD and other open source software

Reasonable expectation of privacy
Most legal systems recognize a right to privacy
US 4h amendment "reasonable expectation of privacy"
nothing to hide argument is short-sighted

Third party doctrine - if you voluntarily give information to third parties you have no reasonable expectation of privacy
1967 US v. Katz - wiretapping a public phone booth is a search and requires a warrant
76 U v Miller - no privacy in banking records
79 smith v. maryland no privacy in phone records
82 - smtp standardized
84 - pop standardized
86 - ECPA - emails left unopened for 180 days are abandoned and not private, opened emails are not private
88 - imap standardized

Possession is 9/10 of the law
Agreeing to boilerplate terms of service results in the abandonment of most of your individual rights
DRM doesn't work well
copies are economically almost free 
copying does not harm the original
cost in data lies in creation, transmission, and storage
Privacy and Copyright are human notions we put on data, not an inherent property of data
interactions between human beings is generally based on information. with larger scope data becomes predictable
A credit score or other single attributed numbers can be an example of this.

I built a server using older components
the server has many different jails 
residential emails - no ports were blocked so the hoome email server is the first mx
moved to OpenSMTPD
Two backup MXs using Digital Ocean in NY and CA
Mail is delivered to Dovecot via LMTP

IMAP
Dovecot is becoming a monoculture, but ceres is an alternative
IMAP + STARTTLS only
Works great with Evolution/Thunderbird/K9
Sieve Filtering works well, but the documentation is difficult

Do not send directly from a dynamic IP, use a relay
Backup MXs are already there and make great relays
not much spam
Per-website emails allow you to throw away emails if they are compromised.
additional spam filtering will be added thanks to BSDCAN tutorial

File Sharing
take the time to think out requirements
FTP
nothing special
SFTP
secured with SSH
easy to setup
not easy to use for basic users
SSHFS works well

It is possible to just use Apache

Owncloud
loses files occasionally
easy to user

Syncthing
 work well
 basic users won't learn to use

Personal assistant AI (eg Siri)
- CPU intensive
- necessary?

Simplify!
- Extensive configuration is useful, but can damage user friendability
- basic users don't mind mediocre performance in exchange for usability

Multidirectional file syncing is still a major problem
NFS isn't working
