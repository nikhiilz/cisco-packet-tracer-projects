creating a router-on-stick simulation using
-2 pcs
-1 switch
-1 router

Assing IP to both the PCs as 192.168.1.1 and 192.168.2.1

on the switch, perform the following

the ports which are connected to PCs, we need to convert them into access port using the following command

type interface x in global configuration mode to switch to port x, this will put us into interface configuration mode
Switch(config)#interface f0/1

type, switchport mode access in interface configuration mode to make the interface as access-port
Switch(config-if)#switchport mode access

perform the same for interface f0/2
Switch(config)#interface f0/2
Switch(config-if)#switchport mode access

Now, we do the same way for the interface which connects to the router but here, we will convert the interface into trunk port
Switch(config)# interface f0/3
Switch(config)# switchport mode trunk



Assing the two PCs different VLANs, vlan 10 and vlan 20

type vlan 10 in global config mode to access vlan 10, this will put us into vlan configuration mode
Switch(config)# vlan 10

type name IT in vlan-configuration mode, to name the vlan as IT
Swithc(config-vlan)#name IT

now, assign this vlan 10 to interface f0/1, for that
type interface f0/1 to get into interface configuration mode
Switch(config)# interface f0/1

type switchport access vlan 10 to assing it vlan 10
Switch(config-if)# switchport access vlan 10

Perform the same for interface f0/2 to assing it vlan 20 as Sales
Switch(config)# vlan 20
Switch(config-vlan)# name Sales
Switch(config-vlan)# interface f0/2
Switch(config-if)# swithcport access vlan 20



In the Router, perform the following

We will first divide the interface f0/3 into two subinterfaces as f0/3.1 and f0/3.2
type interface f0/3.1 in the global configuration mode to divide the interface into f0/3.1 sub-interface. This will put us into sub-interface configuration mode
router(config)# interface f0/3.1

type encapsulation dot1Q 10 to bind the interface f0/3.1 to vlan 10
router(config-subint)# encapsulation dot1Q 10

type ip add 192.168.1.2 255.255.255.0, to assign it IP
router(config-subint)# ip add 192.168.1.2 255.255.255.0

similarly, we will create interface f0/3.2 and bind it to vlan 20. Also assing it ip 192.168.2.2
router(config)#interface f0/3.2
router(config-subint)#encapsulation dot1Q 20
router(config-subint)#ip add 192.168.2.2 255.255.255.0



type interface f0/3 to get to interface f0/3 and type no shut to turn it on
router(config)# interface f0/3
router(config-if)# no shutdown



Now, assing the IPs of interfaces f0/0.1 and f0/0.2 as default gateways for the PCs belonging to their VLANs



done~

we can try pinging from the PCs to see if our simulation works

