# boys_and_girls_day_28_04_2022
School project for kids grade 5-7

We created together a script to search in a leaf-spine evpn-vxlan setup for a mac address (44:38:39:00:00:11 or 15 which would be host1 or host3):

cumulus@oob-mgmt-server:~/ON-10/step-api-py$ ./testmac 44:38:39:00:00:11
Config File available
Verifying supplied Adress
The Adress 44:38:39:00:00:11 is valid and will be used

192.168.200.2 reachble via OOB
192.168.200.3 reachble via OOB
192.168.200.4 reachble via OOB
192.168.200.5 reachble via OOB


192.168.200.6 reachble via OOB
192.168.200.7 reachble via OOB
192.168.200.8 reachble via OOB
192.168.200.9 reachble via OOB


Device leaf1   192.168.200.2   is based on VX
Device leaf2   192.168.200.3   is based on VX
Device spine3  192.168.200.4   is based on VX
Device spine4  192.168.200.5   is based on VX
Boys & Girls day 28.04.2022, Hamburg Germany
Supporting one or two spines as MVP implementation

Starting verification for : 44:38:39:00:00:11

Verifying switch 192.168.200.2  discoverd as leaf1:
FDB                 uses      : 44:38:39:00:00:11 via swp8
FDB                 vlan : 10
RM arp cache        sees      172.16.10.18            local        active   44:38:39:00:00:11
0/0
RM arp cache        sees      fe80::4638:39ff:fe00:11 local        active   44:38:39:00:00:11
0/0
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]:[32]:[172.16.10.18]
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]:[128]:
BGP default vrf                                   172.16.100.2                           0 65100 65102 i
! vni = 10 hard coded for MVP
BGP mac vrf                   *> [2]:[0]:[48]:[44:38:39:00:00:11]:[32]:[172.16.10.18]
BGP mac vrf                   *> [2]:[0]:[48]:[44:38:39:00:00:11]:[128]:


Verifying switch 192.168.200.3  discoverd as leaf2:
FDB                 uses      : 44:38:39:00:00:11 via vxlan48
FDB                 vlan : 100
FDB                 uses      : 44:38:39:00:00:11 via vxlan48
FDB                 uses the tunnel destination of 172.16.100.1
RIB                           172.16.100.1   * fe80::4638:39ff:fe00:7, via swp2, weight 1
RIB                           172.16.100.1   * fe80::4638:39ff:fe00:9, via swp1, weight 1
FIB                           172.16.100.1 nhid 57 proto bgp metric 20
FIB                           Kernel 4.19.0-cl-1-amd64 uses "next hop groups", discovering next layer
FIB                                id 57 group 46/51 proto zebra
FIB                                      1.: nh group: 46
FIB                                     ['id 46 via fe80::4638:39ff:fe00:7 dev swp2 scope link proto zebra ']
FIB                                      2.: nh group: 51
FIB                                     ['id 51 via fe80::4638:39ff:fe00:9 dev swp1 scope link proto zebra ']
RM                  sees      : 44:38:39:00:00:11 via 172.16.100.1
RM arp cache        sees      172.16.10.18            remote       active   44:38:39:00:00:11 172.16.100.1
0/0
RM arp cache        sees      fe80::4638:39ff:fe00:11 remote       active   44:38:39:00:00:11 172.16.100.1
0/0
BGP default vrf               *  [2]:[0]:[48]:[44:38:39:00:00:11]
BGP default vrf                                   172.16.100.1                           0 65100 65101 i
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]
BGP default vrf                                   172.16.100.1                           0 65100 65101 i
BGP default vrf               *  [2]:[0]:[48]:[44:38:39:00:00:11]:[32]:[172.16.10.18]
BGP default vrf                                   172.16.100.1                           0 65100 65101 i
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]:[32]:[172.16.10.18]
BGP default vrf                                   172.16.100.1                           0 65100 65101 i
BGP default vrf               *  [2]:[0]:[48]:[44:38:39:00:00:11]:[128]:
BGP default vrf                                   172.16.100.1                           0 65100 65101 i
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]:[128]:
BGP default vrf                                   172.16.100.1                           0 65100 65101 i
! vni = 10 hard coded for MVP
BGP mac vrf                   *  [2]:[0]:[48]:[44:38:39:00:00:11]:[32]:[172.16.10.18]
BGP mac vrf                   *> [2]:[0]:[48]:[44:38:39:00:00:11]:[32]:[172.16.10.18]
BGP mac vrf                   *  [2]:[0]:[48]:[44:38:39:00:00:11]:[128]:
BGP mac vrf                   *> [2]:[0]:[48]:[44:38:39:00:00:11]:[128]:


Verifying switch 192.168.200.4  discoverd as spine3:
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]:[32]:[172.16.10.18]
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]:[128]:
! vni = 10 hard coded for MVP


Verifying switch 192.168.200.5  discoverd as spine4:
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]:[32]:[172.16.10.18]
BGP default vrf               *> [2]:[0]:[48]:[44:38:39:00:00:11]:[128]:
! vni = 10 hard coded for MVP

