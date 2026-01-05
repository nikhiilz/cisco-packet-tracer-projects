creating a basic ntp manipulation using- 

- 1 server
- 1 router

assing ip to both the devices, see that ntp is already active by default in the server

in the router CLI, perform the follwing

type show clock in the user-privileged executive mode to see the current clock
router#show clock

type ntp server x in the global-configuration mode where x is the address of our ntp server, which is 192.168.1.2 in our case
router(config)#ntp server 192.168.1.2

type clock timezone GMT -4 to set the timezone, here GMT is the timezone, -4 is the actual time different from the universal timezone
router(config)#clock timezone GMT -4
router(config)#exit

this will take some time to reflect, if we want to see the details we can run show ntp associations command in the user-priviliged mode to see the offset value, if it is set to 1, it means the time is changed otherwise the offset won't be 1 and it will still be requiring some time to reflect