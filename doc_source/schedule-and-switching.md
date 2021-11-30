# Multiple\-input channels and the schedule<a name="schedule-and-switching"></a>

Input switching works as follows: You create a channel that contains more than one input attachment\. After the channel is created, you go into the schedule for that channel and add input switches, to create rules for moving from one input attachment to another\. When you start the channel, the channel will automatically switch inputs according to the schedule\.

To work successfully with multiple\-input channels, remember the following\.

**The schedule exists inside the channel**

The schedule does not exist separately from the channel\. On the console, you find the schedule in the details page for an existing channel\.

**There is no implicit switching**

With a multiple\-input channel, you must add input switches to the schedule to instruct the channel to switch\. A channel that contains more than one input attachment won't switch to the next input attachment in the list of input attachments unless the schedule specifies to do so\.

**There is no "main" input**

With a multiple\-input channel, you must think of the input attachments as a *pool* of inputs all with equal status\. There isn't one input that is the main input, that the channel returns to when it has nothing else to ingest\.