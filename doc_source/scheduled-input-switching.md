# Input switching in AWS Elemental MediaLive<a name="scheduled-input-switching"></a>

You can set up an AWS Elemental MediaLive channel to ingest multiple sequential inputs, rather than setting it up to ingest only one input\. You set up this *multiple\-input channel* by attaching more than one input to the channel, and then adding actions in the channel's schedule that specify when to switch from one input to another\. 

**Topics**
+ [About multiple\-input channels and input switching](ips-overview.md)
+ [Rules and limits for input switches](ips-limits.md)
+ [Setting up for input switching](setup-ips.md)
+ [Deleting actions from the schedule](ips-manage-schedule.md)
+ [Starting and restarting a channel that has multiple inputs](ips-start-channel-multi-inputs.md)