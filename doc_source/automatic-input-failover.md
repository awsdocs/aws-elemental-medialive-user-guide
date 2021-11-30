# Implementing automatic input failover<a name="automatic-input-failover"></a>

When you set up the inputs for a channel, you can set up two push inputs as an *input failover pair* \(or failover pair\)\. Setting up this way provides resiliency for the source, in case of a failure in the upstream system, or a failure between the upstream system and the channel\. 

You can configure the channel so that MediaLive detects one or more of the following problems in the input:
+ Black video \(video failure\) – MediaLive will perform a failover if content is considered black for the specified period\.
+ Audio silence \(audio failure\) – MediaLive will perform a failover if the specified audio selector is silent for the specified period\.

Each input in the input pair provides content to the channel\. One of the inputs is the *active * input and one is on *standby*\. MediaLive ingests both inputs, in order to always be ready to switch, but it usually discards the standby input immediately\. If the active input fails, MediaLive immediately fails over and starts processing from the standby input, instead of discarding it\.

**Note**  
Before you decide to implement automatic input failover, you should read about [pipeline redundancy](plan-redundancy-mode.md), which is another form of channel resiliency\. You might decide to implement one or both of these features\. 

**Topics**
+ [Automatic input failover in a single\-pipeline channel](aif-single-pipeline-how.md)
+ [Automatic input failover in a standard channel](aif-standard-pipeline-how.md)
+ [Setting up automatic input failover with CDI inputs](aif-setup-cdi.md)
+ [Setting up automatic input failover with MediaConnect inputs](aif-setup-emx.md)
+ [Setting up automatic input failover with RTMP and RTP inputs](aif-setup-other-inputs.md)
+ [Changing the roles of the failover pair](aif-setup-inverting.md)
+ [Starting the channel](aif-behavior-startup.md)
+ [Manually forcing a failover](aif-and-input-switching-failoverpair.md)
+ [Automatic input failover and input switching](aif-and-input-switching.md)