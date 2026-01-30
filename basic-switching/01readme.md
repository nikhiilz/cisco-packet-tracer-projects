we will be creatin a basic VLAN using :
-1 switch
-4 PCs

assign IP to all the PCs

type vlan 10 in the terminal configuration mode, this will put us in the VLAN configuration mode
Switch(config)#vlan 10

type name x, in the vlan config mode, where x is the name of our vlan, it is dept1 in our case
Switch(config-vlan)#name dept1

similarly, access vlan 20 and assign it name dept2
Switch(config)#vlan 20
Switch(config-vlan)#name dept2

Now, we have given the name dept1 and dept2 to vlans 10 and 20 respectively. We will now assign the interfaces to each of the vlans in a way : f0/1 and f0/2 to VLAN 10 and f0/3 and f0/4 to VLAN 20

type interface f0/1 in the terminal-config mode to get into interface config mode
Switch(config)#interface f0/1

type switchport access vlan 10 in the interface config mode to assign it a vlan, which is vlan 10 in our case
Switch(config-if)#switchport access vlan 10

similarly, repeat for interfaces f0/2, f0/3 and f0/4

once assigned, we can run show vlan brief in user privileged mode to see the vlan configuration, it will also list us with names we have assigned to vlan
Switch#show vlan brief

NOTE: if we try pinging from dept1 to dept2, ping will be successfull since trunking and DTP is enabled by default but if we want to disable it, we can put all the ports into access mode. To do so,

type interface f0/1, to get into interface config mode
Switch(config)#interface f0/1

type switchport mode access in the interface config mode to make this port an accessport
Switch(config-if)#switchport mode access

similarly, repeat for the interfaces f0/2, f0/3 amd f0/4
now if we try pining, it won't go through

done1