configuring a basic EIGRP simulation including:
-2 routers
-2 switches
-4 PCs

Assing IP addresses to all the devices, also assign default gateway in PCs

In Router0, we have to assing an ASN and advertise the network 192.168.1.0 and 192.168.2.0, so perform the follwing

type router eigrp x in the global configuration mode,it will assing the ASN to the router where x will be our ASN for the route here I am choosing 1, this will also put us in the router configuration mode
router(config)#router eigrp 1

type network 192.168.1.0 in the router configuration mode to advertise this network
router(config-router)#network 192.168.1.0

type network 192.168.2.0, to advertise this network
router(config-router)#network 192.168.2.0


In Router1, we have to assing an ASN and advertise the network 192.168.2.0 and 192.168.3.0, so perform the same

type router eigrp x in the global configuration mode, to assing ASN,make sure it is the same as our first Router otherwise EIGRP won't work. This will now put us in router configuration mode
router(config)#router eigrp 1

type network 192.168.2.0 in router configuratin mode, to advertise this network
router(config-router)#network 192.168.2.0

type network 192.168.3.0, to advertise this network
router(config-router)#network 192.168.3.0



done!
we can try pinging to check our connectivity. Also, we can try running the command show ip protocols in the user privileged mode of each router to check if EIGRP protocol is running there
router#show ip protocols