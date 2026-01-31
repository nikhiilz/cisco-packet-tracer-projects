creating a basic RIP protcol simulation using
-2 routers
-2 switches
-4 PCs

assign IP to all the devices, use default gateways for the PCs

For RIP to work:
-we have to enable RIP on both Router1 and Router2
-we advertise the networks(After RIP is assigned, we tell the Routers about directly-attached networks to them)

We go to Router1 and perform the following

type router rip in the global configuration mode, this will put us in the Router configuration mode and tells the router to use RIP protocol for routing
router(config)#router rip

type network 192.168.1.0 in the Router Configuration Mode, this will tell the router about the directly connected network 192.168.1.0 in the router
router(config-router)#network 192.168.1.0

similarly, advertise the network 192.168.2.0
router(config-router)#network 192.168.2.0


We go to Router2 and perform the following

type router rip in the global configuration mode, this will put us in the Router Configuration and tells it to use RIP protocol
router(config)#router rip

type network 192.168.2.0 in the router configuration mode, this will tell the Router about the network 192.168.2.0, which is directly attached to it
router(config-router)#network 192.168.2.0

similarly, advertise network 192.168.3.0
type network 192.168.3.0
router(config-router)#network 192.168.3.0


done!

to see, run show ip route in the user-privileged exec mode


NOTE: The similar functionality can be performed using GUI method, simply go to config tab, select RIP under Router and type network, click "add"