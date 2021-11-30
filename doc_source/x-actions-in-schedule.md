# Types of actions in the schedule<a name="x-actions-in-schedule"></a>

The schedule is a list of actions that a channel performs as it is running\. You can use actions to do the following:
+ Switch the input that the running channel is ingesting\.
+ Prepare an input that is associated with an immediate input switch, in order to reduce the delay that occurs when MediaLive performs the switch\.
+ Insert a static image overlay \(an image layered over the underlying video\) into the running channel\. 
+ Insert a motion graphics overlay into the running channel\. 
+ Insert SCTE\-35 messages into the running channel\.
+ Insert ID3 metadata into the running channel\.
+ Insert ID3 segment tags into the running channel\.
+ Pause one or both of the pipelines in the channel\.
+ Unpause one or both of the pipelines in the channel\.

For more information, see [How schedule actions work](sched-how-actions-work.md)\. 