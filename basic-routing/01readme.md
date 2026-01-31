creating a basic static-routing network simulation usign the Exit Interface method of defining routes usign

-4 pcs
-2 switches
-2 routers

Assign IP addresses to all the networks, also  include default gateways in all the PCs

The Router1 knows the path to network 192.168.1.0 and 192.168.2.0 but we need to assign a path to network 192.168.3.0
We will use the exit-interface method for defining the routers

in Router1, perform the following:

type ip route 192.168.3.0 255.255.255.0 f0/1 in the global-configuration mode. This defines that any packet which is destined for the network 192.168.3.0 should be exited through the interface f0/1. 255.255.255.0 is the subnet for the destined network
Router1(config)#ip route 192.168.3.0 255.255.255.0 f0/1

Similarly, we need to define the path for network 192.168.1.0 in Router2

in Router2, perform the following:

type ip route 192.168.1.0 255.255.255.0 f0/0

done!

to see the routes, simply type show ip route in the user-privileged exec mode
Router#show ip route