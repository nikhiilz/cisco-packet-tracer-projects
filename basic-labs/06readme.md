creating a basic tftp simulation using a server and a router where we will be saving a file from the server to the router

- 1 router
- 1 server

setup IP addresses in both the devices

in the router CLI, perform the following

type copy tftp flash: in the user-previleged executive mode
Router#copy tftp flash:

this will now ask us for the address of the remote host: type server's address

next, type the name of the source file from the server that we want to copy, we can, for now, manually look for the file and copy it

I have choosen asak842-k8.bin

next, it will ask us for the filename that we are going to choose when we paste it in the router's flash memory

I have choosen pastefile.txt for my file

save it and then we can again type dir to list for the files in the router's flash memory to see if the file is available there