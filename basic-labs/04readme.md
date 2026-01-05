creating basic dns server and http server using- 

- 1 switch
- 1 pc
- 2 servers(one is DNS, another is http)

start by manually assigning IP to each of the devices. The IP which is assigned to the DNS server should be assigned to each device as DNS server's address

in the http server, under services tab - there is http service which is on by default, if you want to edit the index.html file, it would be your choice

to create a DNS entry, go to DNS services in the DNS Server, turn them on and do the following

-in the name column, add xyz.com
-in the address column, add your http server's address which is 192.168.1.2 in my case
-click on add button


no access the web browser from the pc and type xyz.com in the url bar the following will the result of index.html, which is the file saved in our http server