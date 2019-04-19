# What Happens at Runtime<a name="ips-runtime-behavior"></a>

When you start the channel, MediaLive takes a short time to get the channel ready to run\. 

As soon as the channel is ready, MediaLive looks at the schedule to determine if there is an input switch with a start time that is now or that is overdue: 
+ If it finds this action, it switches to that input and starts ingesting\. 
+ If it does not find this action, it starts ingesting the first input attachment listed in the channel\.