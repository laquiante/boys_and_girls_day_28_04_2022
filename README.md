# boys_and_girls_day_28_04_2022
School project for kids grade 5-7

We created together a script to search in a leaf-spine evpn-vxlan setup for a mac address (44:38:39:00:00:11 or 15 which would be host1 or host3):

cumulus@oob-mgmt-server:~/ON-10/step-api-py$ ./testmac 44:38:39:00:00:11

[SNIP]
  
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
  
[SNIP]  
  
