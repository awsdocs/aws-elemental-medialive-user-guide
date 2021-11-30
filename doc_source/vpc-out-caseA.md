# Use case A – no VPC inputs<a name="vpc-out-caseA"></a>

This use case applies if the channel won't have inputs that use the VPC:
+ No MediaConnect inputs
+ No CDI inputs
+ No RTMP VPC inputs
+ No RTP VPC inputs 

Here is a diagram of the setup, when the channel is a standard channel\. In this example, the channel has two output groups\. Assume that the destinations of both the output groups are on EC2 on your VPC\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\vpc-delivery-1.png)

**Single\-pipeline channels**

You must identify subnets for the following locations:
+ The channel endpoint for pipeline 0 \(in the blue box\)\.
+ The destinations for pipeline 0 \(in the orange box\)\.

Your setup must observe these rules for VPCs and subnets:
+ You can set up the locations on any number of VPCs\.
+ There is no requirement for any of the VPCs or subnets to be the same or different\.

Your setup must observe these rules for the Availability Zones of the subnets that you identify:
+ The channel endpoint can be in the same Availability Zone as the destination \(or destinations\)or in a different Availability Zone\. If it is in a different Availability Zone, you will incur outgoing data transfer charges\. For more information about pricing, see [https://aws.amazon.com/medialive/pricing/](https://aws.amazon.com/medialive/pricing/)\. 

**Standard channels**

You must identify subnets for the following:
+ The two channel endpoints \(in the blue box\)\.
+ All the destinations \(in the orange box\)\.

Your setup must observe these rules for VPCs and subnets:
+ You can set up the locations on any number of VPCs\.
+ The subnets for the channel endpoints must be different from each other, but the two subnets must be on the same VPC\.
+ There are no other requirements for subnet uniqueness in any of the subnets that you identify\.

Your setup must observe these rules for the Availability Zones of the subnets that you identify:
+ The Availability Zones for the two channel endpoints must be different\. 
+ Each channel endpoint can be in the same Availability Zone as the destination \(or destinations\)\. Or it can be in a different Availability Zone\. If you choose to set up with different Availability Zones, you will incur outgoing data transfer charges\. For more information about pricing, see [https://aws.amazon.com/medialive/pricing/](https://aws.amazon.com/medialive/pricing/)\. 