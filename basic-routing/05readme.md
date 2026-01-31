configuring a basic OSPF simulation using:

-2 routers
-2 switches
-4 PCs

configure IP addresses on all the devices

now, to setup OSPF on Router0, perform the following

type router ospf x in the global configuration mode, which will put us in the router configuration mode where x is process ID, which is 1 in our case
Router(config)#router ospf x

We have enabled ospf with a process ID on the router, now we will be advertising both the networks on this router, which is 192.168.1.0 and 192.168.2.0
type network x y area z in the router configuration mode, where x is the network address which is 192.168.1.0, y is the wildcard, which is 0.0.0.255 for this address and z is the area code, which is 0 in our case. Using this, we will advertise both 192.168.1.0 and 192.168.2.0
Router(config-router)#network 192.168.1.0 0.0.0.255 area 0
Router(config-router)#network 192.168.2.0 0.0.0.255 area 0

In the similar manner, we can enable OSPF on Router1 and advertise the networks 192.168.2.0 and 192.168.3.0 with process IDs and area IDs respectively
Router(config)#router ospf 1
Router(config-router)#network 192.168.3.0 0.0.0.255 area 0
Rotuer(config-router)#network 192.168.2.0 0.0.0.255 area 0



We can wait for approx 30 seconds for the routers to update and try pinging to PC0 to PC2

Done!

