creating a Port-Security simulation using
- 1 Switch
- 2 PCs

first, assing IP to both the PCs
put the interfaces of the switch in a range to configure them together > put them in access mode > enable port security > only allow one MAC address per port > provide MAC address(either statically or dynamically) > define the action on unauthorized device detection

type interface range f0/1 - f0/2 in global configuration mode to configure them together. This will put us in inter-range configuration mode
switch(config)# interface range f0/1 - f0/2

type switchport mode access in the int-range configuration mode to put both the interfaces in that range into access port
switch(config-int-range)# switchport mode access

type switchport port-security to enable port security
switch(config-int-range)# swtichport port-security

type swtichport port-security maximum 1, to set the maximum number of MAC address on each port as 1(it could go from 1-135)
switch(config-int-range)# switchport port-security maximum 1

type switchport port-security mac-address sticky, to set the MAC-address dynamically which will be choosen automatically for the port based on the device which is connected first
switch(config-int-range)# switchport port-security mac-address sticky

type swithcport port-security violation shutdown, to set the action which will be executed in case of unknown device detection
switch(config-int-range)# switchport port-security violation shutdown

done1

we can try replacing one of the PCs with a new one and then notice thatn the link goes down