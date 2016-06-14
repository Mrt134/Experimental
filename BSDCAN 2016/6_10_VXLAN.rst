.. _use vxlan:

Using VXLAN: Networking virtual machines, jails, and other fun things on FreeBSD by John Nielsen 6/10/16 1000
=============================================================================================================

VXLAN in Brief
--------------

Virtual Extensible local area Networking

Creates overlay networks by encapsulating ethernet frames in udp/ip with an associated 24bit virtual network identifies

virtual tunnels

hosts are called vteps

wikipedia graphic "quick review of ip protocol layers

the original eth fram is prepended with a vxlan header

they form the data packet of the outer layers
vlan:

virtual local area network
layer 2 multiplexing enhancement allowing up to 4094 virtual layers 2 networks
Vlan has be to be ethernet
whole network has to be single layer 2 segment (vlans don't cross routers)
limmited to 4094 vlans
Tunnels
point to point connections between two end points
typicially encaps ehter l2 or up l3 traffic withihn ip or tcp udp
great for links between two hosts
good for multiple links in a star topology

tunnel limits

dont scale well
  n hosts the number of tunnels needed is n2 - n ---2
  tunnels needed grows exponentially with the number of endpoints

Vxlan benefits
 one virtual tunnel per hosts
 no switch support requiered
 forwarding table is auto created and maintained
Vxlan limits
 each segment must support multicast
 some implements can use out of band discovery instead of multicast
encaps adds 50 bytes to each packet
  same for 1 -1 tunels
  need larger mtu on outer network or smaller mtu on inner networks
cpu costs (nics are supporting vxlans more often though)
how does vxlan work
 virtual interface for each network to be used on that host
 host maintains forwarding tbale for eeach interface maps inner and outer mac addresses
 packets sent over the o
Sending packets
 look up mac address, if match then packet encapped and sent to remot vtep directly,
Receiving packets
where is it available
FreeBSD 10.2
Tips
usse unique multicast address for each vni
  upper end of ran is classified by the IANA
use the official udp port 4789
remember to adjust the firewall on your vteps
  don't forget multicast
Use Cases
 Bhyve vms
Bridging ethernets
 Interfaces have to be ethernet like to be added
 layer 2 techs can work too
 wireless aop can be bridged, no wireless stations
 all support up and multicast.
networking between vnet jails
 vnet jails of FreeBSD have their own network stacks isolated from the hosts
  host side can be added to a bridge and other side is constricted to a jails
 jails can communicate with other jails on the same vxlan
 
Q: earlier you said one vxlan per point but now it appears differently?
A: vxlan per point under certain conditions

Demos
(FreeBSD)

ifconfig vxlan 1234 create vxlanid 1234 vxlanlocal 192.blah vxlandev vtnet0 vxlangroup 239.blah

editing /etc/rc.conf can allow for vxlans to be created upon every startup.
jail and vm network

freeBSD is trying to do a few things to get ipv6 fully functional with vxlan.
interopability is fine between various distros and os'
vxlan has a significant learning
talk size: about 30+ people