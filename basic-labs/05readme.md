creating a basic ftp simulation using

-1 server
-1 switch
-1 pc

this server will be our ftp server
assign ip to the pc and the server

in the services tab in server, select ftp and do the following

-enter a desired username with the password and select permission to give to that user
-select add

from the command prompt in the pc, type the following


ftp x
where x will be our ftp server's ip and this will then ask us for the username/password 

once logged in, we can then list the directories

suppose we want to save a file on this server, then what we can do is open the text editor in the pc, type a file and save it. Suppose we saved it with the name didit.txt in our case

now to save this file on the server, run the following command

put didit.txt

next if you list all the files, the didit.txt file will be on the server