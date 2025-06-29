Cisco Multi-VLAN Network Lab – Device Configuration Guide



**Core Switch (Layer 3 Switch)**

enable

configure terminal



hostname CoreSwitch

ip routing

spanning-tree mode pvst



! VLAN Interface Configuration (SVIs)

interface Vlan10

&nbsp;ip address 192.168.10.1 255.255.255.0

&nbsp;ip helper-address 192.168.99.10

&nbsp;no shutdown

exit



interface Vlan20

&nbsp;ip address 192.168.20.1 255.255.255.0

&nbsp;ip helper-address 192.168.99.10

&nbsp;no shutdown

exit



interface Vlan30

&nbsp;ip address 192.168.30.1 255.255.255.0

&nbsp;ip helper-address 192.168.99.10

&nbsp;no shutdown

exit



interface Vlan40

&nbsp;ip address 192.168.40.1 255.255.255.0

&nbsp;ip helper-address 192.168.99.10

&nbsp;no shutdown

exit



interface Vlan50

&nbsp;ip address 192.168.50.1 255.255.255.0

&nbsp;ip helper-address 192.168.99.10

&nbsp;no shutdown

exit



interface Vlan60

&nbsp;ip address 192.168.60.1 255.255.255.0

&nbsp;ip helper-address 192.168.99.10

&nbsp;no shutdown

exit



interface Vlan99

&nbsp;ip address 192.168.99.1 255.255.255.0

&nbsp;no shutdown

exit



! Trunk Links to Aggregated Switches

interface FastEthernet0/1

&nbsp;switchport trunk encapsulation dot1q

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 10,20,30

exit



interface FastEthernet0/2

&nbsp;switchport trunk encapsulation dot1q

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 40,50,60

exit



interface FastEthernet0/4

&nbsp;switchport mode access

&nbsp;switchport access vlan 99

exit





**Aggregated Switch 1**



enable

configure terminal



hostname Aggregated1

spanning-tree mode rapid-pvst



interface FastEthernet0/1

&nbsp;switchport trunk encapsulation dot1q

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 10,20,30

exit



interface FastEthernet0/2

&nbsp;switchport trunk encapsulation dot1q

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 30

exit



interface FastEthernet0/3

&nbsp;switchport trunk encapsulation dot1q

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 10,20

exit



**Aggregated Switch 2**



enable

configure terminal



hostname Aggregated2

spanning-tree mode pvst



interface FastEthernet0/1

&nbsp;switchport trunk encapsulation dot1q

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 40,50,60

exit



interface FastEthernet0/2

&nbsp;switchport trunk encapsulation dot1q

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 40

exit



interface FastEthernet0/3

&nbsp;switchport trunk encapsulation dot1q

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 50,60

exit



 **Access Switch 1 (VLAN 10–20)**



enable

configure terminal



hostname AccessSwitch1

spanning-tree mode rapid-pvst



interface FastEthernet0/1

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 10,20

exit



interface FastEthernet0/2

&nbsp;switchport mode access

&nbsp;switchport access vlan 10

exit



interface FastEthernet0/3

&nbsp;switchport mode access

&nbsp;switchport access vlan 20

exit



**Access Switch 2 (VLAN 30)**



enable

configure terminal



hostname AccessSwitch2

spanning-tree mode pvst



interface FastEthernet0/1

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 30

exit



interface FastEthernet0/2

&nbsp;switchport mode access

&nbsp;switchport access vlan 30

exit



interface FastEthernet0/3

&nbsp;switchport mode access

&nbsp;switchport access vlan 30

exit



**Access Switch 3 (VLAN 40)**



enable

configure terminal



hostname AccessSwitch3

spanning-tree mode pvst



interface FastEthernet0/1

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 40

exit



interface FastEthernet0/2

&nbsp;switchport mode access

&nbsp;switchport access vlan 40

exit



interface FastEthernet0/3

&nbsp;switchport mode access

&nbsp;switchport access vlan 40

exit



**Access Switch 4 (VLAN 50–60)**



enable

configure terminal



hostname AccessSwitch4

spanning-tree mode pvst



interface FastEthernet0/1

&nbsp;switchport mode trunk

&nbsp;switchport trunk allowed vlan 50,60

exit



interface FastEthernet0/2

&nbsp;switchport mode access

&nbsp;switchport access vlan 50

exit



interface FastEthernet0/3

&nbsp;switchport mode access

&nbsp;switchport access vlan 60

exit



**DHCP/DNS Server Configuration**

Ensure the server is placed in VLAN 99, with this configuration:



IP Address: 192.168.99.10



Subnet Mask: 255.255.255.0



Enable DHCP for scopes:



VLAN 10: 192.168.10.0/24



VLAN 20: 192.168.20.0/24



...



Enable DNS service if needed

