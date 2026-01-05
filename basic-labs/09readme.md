creating a basic telnet simulation using a router and a pc where we will be accessing a router from the PC

- 1 router
- 1 pc

setup IP on both the devices

now in the router, perform the following:

type hostname x in the global-configuration mode where x is the name which we will be assigning to our router, in my case, I am choosing RR
router(config)#hostname RR

type enable secret x in the global-configuration mode where x is the password we are setting up for the user-privileged exec mode, so that whoever accesses the privileged mode, they will require a password to access it, in my case, I am choosing a simple password 1234
RR(config)#enable secret 1234

type interface x, to open the inteface on which we have configured the IP and which is being accessed by the PC
type line vty 0 5, using this command, we are setting up the number of people who can access the interface, here it is 0 5 meaning 5 people can access what we call line. line vty meaning virutal teletype line. Also, this command will put us into VTY(Vritual Teletype Line) configuration mode. NOTE: PEOPLE WILL FIRST ACCESS OUR ROUTER USING THIS LINE THEN THEY WILL ACCESS THE REST OF THE ROUTER, BE IT USER MODE OR USER-PRIVILEGED EXEC MODE
RR(config-if)#line vty 0 5

type login to enable login feature and it will allow us to add password to it when somebody tries to access the line
RR(config-line)#login

type password x, where x is the password which we are setting up for the line, I am choosing password line1234 in my case
RR(config-line)#password line1234

now we have setup the router's line using a password and we have also setup the user-priviliged executive mode of the router

to try accessing the router, open cmd in PC 

type telent x, where x is our router's IP which we are accessing using telnet
C:\> telnet 192.168.1.1

enter password of the line to access that line, which is line1234 in our case
RR> (this is router's user mode)

type enable to get into the user-priviliged executive mode of the router
enter password for the router's priviliged executive mode, which is 1234 in our case
RR# (this is the user-privileged executive mode of the router)

done!