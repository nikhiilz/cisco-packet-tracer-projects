creating a basic Ether Channel simulation using
-2 Switches

connecting the two switches using two serial links

we will first bundle the cables for ports f0/1 and f0/2 on both the switches
next, we will give that bundle(channel-group) a number and turn that one

type interface range f0/1 - f0/2 on first switch in global configuration mode to configure multiple interfaces at once. This will also put us in multiple interface configuration mode
switch(config)# int range f0/1 - f0/2

type channel-group 1 mode on in channel configuration mode to set the channel number as 1 and turn it on
switch(config-int-range)# channel-group 1 mode on

perform the same on another switch

done! 

you will see that all the links are utilized and there is not link which is down