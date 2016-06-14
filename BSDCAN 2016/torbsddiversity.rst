.. _torbsddiversity:

The Tor BSD Diversity Project (TDP)
===================================

**Beyond Monocultures: The BSDs in Torland**

Beginning notes:
No affiliation with Tor Project
Tor BSD Diversity is Attila and I (George)
recent upheaval in the news, relevant for all software projects

Monoculture
Bananas have been constantly bred from one species of banana, which increases risk of a single blight killing all food bananas.

Tor is top to bottom a linux monoculture 

most attention/development is in linux relays

https://torbsd.github.io

over 7000 tor relays, 89% on linux
93% of bandwidth pushed is from linux
public relays are spread around a little more, though most are in europe
tor exit relays are distributed more equally, but a loss of 15% would still be devastated.
Everyone wants to break Tor 
endpoint security is still the weak link in the chain
will there be a Tor v2?
**Strengths**
open source, documented
engaging community
public network with low barriers of entry

What is TDP?
------------

launched spring 2015
Seeks to diversify the linux monoculture with Tor.
  - no BSD Tor Browser (TB)
  
  
ports developers are devs too

- lots of users go to which OS supports their ports
- those users won't use an os that doesn't supprt their ports

linux distros have the best supported flavors of Tor, so movement has been greatest in that community.
Tor Browser on OpenBSD
Where standards decide all, therefore it is the easiest OS to port "from".
Don't rely on bloated assumptions, even upstream
 GPG for signing and verifying? signify(1)
 a pretend-developer writes an RNG? arc4random(3)

TB onto OpenBSD: the Problems
  anonymity is a moving target
    a new arms race in surveillance and censorship
    
  Mozilla code is a moving target
  an OpenBSD snapshot is a moving target
  Fitting into the ports infrastucture is difficult
    is upstream listening
    bash is a dependency or a cancerous tumor?
Portability Demands Standards
bash exists everywhere, but is a vulnerability
Write not to be understood, but rather so that you can't be misunderstood.

Tor is not the perfect solution. Tor can be compromised by an adver with a full global network fiew, watching critical flows and sitting on backend routers
Disrupt the monoculture
 - run BSD relays
 - encourage {university, firm, ngo}:NYI, check
 - join Tor-BSD mailing list
 - Fork/contribute to https://github.com/torbsd/openbsd-ports/
    - additional effort would be helpful
    - hardened BSD?
    - contributions to documentation
    - sane optimization, understanding the realties
It is very difficult to test the tor network, as the randomized element prevents an accurate sample from being taken

If you want to run a exit node, remember:
- no access to exit logs
- don't use relatable ip addresses
- btr should be you, not provider
- put up a website with messaging about an exit node
- run as a bridge if using from home

Legitimizing the Tor network will likely take a corporate sponsor(s), like Mozilla's contribution. 
