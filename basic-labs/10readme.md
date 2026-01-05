creating a basic ssh manipulation using

- 2 pcs
- 1 switch
- 1 router

assing IP address to all the devices in the network

now, perform the following in the router

type hostname x in the global configuration mode to set the name of the router to x, I am using RR
Router(config)#hostname RR

type enable secret x, to set a secret password on the global configuration mode so that whoever accesses the router's privileged mode would require a password,I am using global123
RR(config)# enable secret global123

type ip domain-name x, to create a domain for loggin into ssh, I am using xyz.in
RR(config)#ip domain-name xyz.in

type crypto key generate rsa, to generate a pair of keys using RSA to be used since SSH requires keys for login purposes. Note that next, the prompt will ask us for the size of keys to be used in bits, I will choose 1024 and also note that these keys won't be exportable somewhere
RR(config)#crypto key generate rsa
How many bits in the modulus [512]: 1024

type username x password y, to create a username and password which will be required to login into ssh under the domain xyz.com, I am choosing uname tryingssh with password sshlogin123
RR(config)#username tryingssh password sshlogin123


now, we will setup a virutal teletype line which will be accessed by someone on a specific port

type line vty 0 x, this will enable virtual teletype line where x defines the number of people who can access this line, we are choosing 5
RR(config)#line vty 0 5

type transport input ssh, this will enable the ssh that we setup on the router to be working on this line
RR(config-line)#transport input ssh

type login local, this will enable the username&password that we setup locally to be used as login on this line
RR(config-line)#login local

done!

to check the ssh configuration that we have done, we can tryping sshing from one of the PCs-
open cmd and type ssh -l tryingssh 192.168.1.1, where tryingssh is the username and 192.168.1.1 is our ssh device, router in this case
C:\>ssh -l tyrpingssh 192.168.1.1

this will ask us for the password for the sshing user tryingssh, here it is sshlogin123

this will put us into router's user mode. To get into user-privileged executive mode, type enable and then the password for the global privileged executive mode that we setup, global123 here

Done!