# Working with inputs in AWS Elemental MediaLive<a name="creating-input"></a>

An *input* is a video asset that is to be transcoded and packaged\. The source of the video asset is the [upstream system](container-planning-workflow.md)—the system in your end\-to\-end workflow whose activities occur before those of AWS Elemental MediaLive\. The upstream system can be on the public internet or in a virtual private cloud \(VPC\) that you created using Amazon Virtual Private Cloud \(Amazon VPC\)\.

An AWS Elemental MediaLive input holds information that describes how the source content on the upstream system and the MediaLive channel are connected\. 

## Inputs, input security groups, and channels<a name="input-isg-channel"></a>

The input is one of the components of a MediaLive workflow\. The others are the [input security group](inputsecuritygroups.md) and the [channel](channels.md)\. These three components are linked together\. If the input requires it, an input security group is attached to the input\. Not all inputs have this requirement\. An input is attached to a channel\.

The following rules apply to the linking to an input:
+ The association between an *input* and an *input security group* is defined in the input side\. You set up the association when you create or edit the input\.
+ The association between an *input* and a *channel* is defined on the channel side\. You set up the association when you create or edit the channel\.
+ An input can have only one input security group attached to it\. But that input security group can be already attached to another input; one input security group can "serve" several inputs\. 
+ An input can be attached to only one channel; several channels can't use the same input\. 

**Topics**