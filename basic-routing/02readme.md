creating a static routing simulation using next-hop ip address with the help of
-4 pcs
-2 switches
-2 routers

assign ip addresses to all the devices, also include Default Gateway in all the four PCs 

Router1 knows the path to network 192.168.1.0 and 192.168.2.0 but we need to assing it a route to network 192.168.3.0

In Router1, perform the following

type ip route 192.168.3.0 255.255.255.0 192.168.2.2 in global config mode; where 192.168.3.0 is the network we want to add, 255.255.255.0 is the subnet for that address, and the 192.168.2.2 is the next-hop ip address which will be the exit pathway for network's address

Router1(config)#ip route 192.168.3.0 255.255.255.0 192.168.2.2

Similarly, perform the following for Router2; since it only knows the path for Network 192.168.2.0 and 192.168.3.0

Router2(config)#ip route 192.168.1.0 255.255.255.0 192.168.2.1


done!

to check, try running show ip route in user-privileged exec mode 

Router2#show ip route