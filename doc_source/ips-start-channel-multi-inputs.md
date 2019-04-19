# Starting a Channel That Has Multiple Inputs<a name="ips-start-channel-multi-inputs"></a>

Before you start the channel, make sure that the following are set up:
+ Create actions in the schedule, if appropriate\.

  You can start the channel before or after you have added actions to the schedule\.

  We recommend that you create at least the first few input switches before you start the channel\.

  If the first input attachment listed in the channel is not the input that you want to be ingested first, then you must create an action in the schedule to switch inputs\. Create this action to start on or before the time that you plan to start the channel\.
+ Make sure the inputs attached to the channel are ready:
  + Live inputs \(in other words, all push inputs\) must be already pushing before you start the channel\. A live input must be already pushing even if it is not the first input in the channel\.
  + If the first input in the channel is a file input, it must be ready to be pulled\. 
  + A file input that is not the first input doesn't have to be ready to be pulled until approximately 30 seconds before the switch to the input occurs\. 

**Topics**
+ [What Happens at Runtime](ips-runtime-behavior.md)
+ [Restarting a Channel](ips-restart-channel-multi-inputs.md)