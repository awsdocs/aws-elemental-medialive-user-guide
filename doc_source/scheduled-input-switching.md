# Input Switching in AWS Elemental MediaLive<a name="scheduled-input-switching"></a>

You can set up an AWS Elemental MediaLive channel to ingest multiple sequential inputs, rather than setting it up to ingest only one input\. Here are the main steps:
+ You create multiple inputs\.
+ You create a channel and associate those inputs by setting them up as input attachments\.
+ You create actions in the schedule that specify when to switch from one input to another\. 
+ You start the channel\. MediaLive immediately looks at the schedule to determine the first input to ingest\. It then follows the schedule throughout the running of the channel and switches inputs as required\.

**Note**  
It is not enough to just add multiple inputs to the channel\. You must create actions in the schedule that specify when to switch from one input to another\. Even if you want the inputs to follow each other, you must create actions in the schedule\. Otherwise, the MediaLive channel ingests only the first input\. 

**Topics**
+ [Typical Use Cases](typical-use-cases.md)
+ [Recommended Procedure](ips-recommended-procedure.md)
+ [Rules and Limits for Input Switches](ips-limits.md)
+ [Types of Switches—Fixed, Follow, and Follow Chains](ips-switch-types.md)
+ [Planning the Schedule of Input Switches](ips-planning.md)
+ [Creating Inputs for Input Switching](ips-creating-inputs.md)
+ [Creating a Channel with Multiple Inputs](ips-create-channel-multi-inputs.md)
+ [Setting Up the Schedule with Input Switches](ips-set-up-schedule.md)
+ [Starting a Channel That Has Multiple Inputs](ips-start-channel-multi-inputs.md)