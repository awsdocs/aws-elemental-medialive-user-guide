# Implementing resiliency in the channel<a name="resiliency-channel"></a>

AWS Elemental MediaLive has several features that provide resiliency in the channel:
+ Automatic input failover – You can set up two inputs in an *input failover pair*\. Setting up this way provides resiliency in case of a failure either in the upstream system, or between the upstream system and the channel\. For more information, see [Implementing automatic input failover](automatic-input-failover.md)\.
+ Input loss behavior – You can set up the channel to control how MediaLive behaves when input is lost\. This feature covers all inputs—those that are set up with automatic input failover, and those that aren't\.

  For more information, see [Global configuration \- Input loss behavior](creating-a-channel-step3.md#input-loss-behavior)\.
+ Pipeline redundancy – You can set up the channel with two pipelines, to provide resiliency within the channel pipeline\. This feature is controlled by the channel class feature of the channel\. For more information, see [Implementing pipeline redundancy](plan-redundancy-mode.md)\.