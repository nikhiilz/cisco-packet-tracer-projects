creating a simple network using CLI in router using:

- 4 PCs
- 2 switches
- 1 router

For the PCs, setup the IPs manually, for the router, use the following command in the CLI of router

if it asks for initial config - > type no (it is asking us if we want to load the previous configuration)

Router> (this is the user mode)

type enable to get into the user-privileged config mode
Router# (this is the user-privileged executive mode)

type config terminal to get into the global config mode
router(config)# (this is the global config mode)

type interface x, to get into the interface configuration mode, where x is the selected interface, to know interfaces, we can simply run show interface in the global-configuration mode. NOTE that exit will take us a mode prior. In our case, interfaces are GigabitEthernet0/0/0 and GigabitEthernet0/0/1
router(config-if)# (this is the interface config mode)

type no shut, to activate the interface, meaning no shutdown
type ip address x y, where x is the ip address and y is the subnet to it

exit and repeat the process with another interface

once done, tryig pinging from the PCs to make sure everything is working