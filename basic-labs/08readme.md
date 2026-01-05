setting up a basic smtp and pop server with

- 3 PCs
- 1 switch
- 1 server

setup IP on all the devices
see that under email in server service, both SMTP and POP3 are active by default

we now setup our domain and create three accounts under that domain

do the follwing:
in domain name, type xyz.com
in user, type act1 with pwd 1234
click "+" button, perform the same for the rest of the users which we want to add, we have act2 and act3

now we will setup these three account in our PCs respectively

open email in user 1 pc and do the follwing
in yourname, type user1
in email, type act1@xyz.com(since we will login into user1 with our first user account which is act1)
in incoming mail server, type our SMTP server's ip which is 192.168.1.4
in outgoing mail server, type our POP3 server's ip which is 192.168.1.4
in username, type act1 which we set up earlier
in password, type 1234 which we set up earlier

do the same for user 2 and user 3 PCs

to check if we have succesffully configured, we will try composing email from one user to another user and make sure we click Receive button on the receiving PC's email to make sure we have successfully used POP3 to retrieve email