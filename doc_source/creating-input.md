# Working with Inputs in AWS Elemental MediaLive<a name="creating-input"></a>

An *input* is a video asset that is to be transcoded and packaged\. The source of the video asset is the [upstream system](planning-upstream.md)—the system in your end\-to\-end workflow whose activities occur before those of AWS Elemental MediaLive\. The upstream system can be on the public internet or in a virtual private cloud \(VPC\) that you created using Amazon Virtual Private Cloud \(Amazon VPC\)\.

MediaLive supports specific input types\. For information about the types, see [Supported Input Types and Upstream Systems](inputs-supported-containers.md)\.

**Important**  
Typically, you set up the MediaLive channel as a [standard channel](plan-redundancy-mode.md)\. The procedures in this chapter assume that you have set up in this way\. The procedures therefore refer to an upstream system having two sources that deliver content to two endpoints on the MediaLive input\.   
If you will set up the channel as a single\-pipeline channel, then your upstream system has only one source\. MediaLive creates two endpoints on an input, but only the first endpoint is used\.

## Inputs, Input Security Groups, and Channels<a name="input-isg-channel"></a>

The input is one of the components of a workflow\. The others are the [input security group](inputsecuritygroups.md) and the [channel](channels.md)\. These three components are linked together\. An input security group is attached to an input \(if the input requires an input security group; not all inputs have this requirement\)\. An input is attached to a channel\.

The following rules apply to the linking to an input:
+ The association between an input and an input security group is defined in the input side\. You set up the association when you create or edit the input\.
+ The association between an input and a channel is defined on the channel side\. You set up the association when you create or edit the channel\.
+ An input can have only one input security group attached to it\. But that input security group can be already attached to another input; one input security group can "serve" several inputs\. 
+ An input can be attached to only one channel; several channels can't be attached to the same input\. 
+ If your channel has multiple inputs, you can attach the same input more than once to a channel\. For example, you might have a file to use to fill the time between live events\. You can use this file as often as you want\.

**Topics**