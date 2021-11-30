# Use case B – channel includes VPC inputs<a name="vpc-out-caseB"></a>

This use case applies if the channel includes inputs that use the VPC:
+ MediaConnect inputs
+ CDI inputs
+ RTMP VPC inputs
+ RTP VPC inputs 

Here is a diagram of the setup, when the channel is a standard channel\. In this example, the channel has at least one VPC input\. It also has two output groups\. Assume that the destinations of both the output groups are on EC2 on your VPC\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\vpc-delivery-2.png)

**Single\-pipeline channels**

You must identify subnets for the following locations:
+ The endpoint for the VPC input for pipeline 0 \(in the green box\)\.
+ The channel endpoint for pipeline 0 \(in the blue box\)\.
+ The destinations for pipeline 0 \(in the orange box\)\.

Your setup must observe these rules for VPCs and subnets:
+ You can set up the locations on any number of VPCs\.
+ There is no requirement for any of the VPCs or subnets to be the same or different\.

Your setup must observe these rules for the Availability Zones of the subnets that you identify:
+ The endpoint of the VPC input and the channel endpoint must be in the same Availability Zone\. This rule exists because both these endpoints are inside the channel pipeline, and the pipeline can't start in one Availability Zone and end in another\.

  If the VPC input is already set up in the VPC, it is probably easiest to identify the Availability Zone of that subnet as the shared Availability Zone\. 

  If the VPC input isn't yet set up, make sure that the two subnets are in the same Availability Zone\.
+ The channel endpoint can be in the same Availability Zone as the destination \(or destinations\) or in a different Availability Zone\. If it is in a different Availability Zone, you will incur outgoing data transfer charges\. For more information about pricing, see [https://aws.amazon.com/medialive/pricing/](https://aws.amazon.com/medialive/pricing/)\. 

**Standard channels**

You must identify subnets for the following:
+ The endpoints for the VPC inputs \(in the green box\)\.
+ The channel endpoints \(in the blue box\)\.
+ The destinations \(in the orange box\)\.

Your setup must observe these rules for VPCs and subnets:
+ You can set up the locations on any number of VPCs\.
+ The subnet for the VPC inputs in pipeline 0 and the VPC inputs in pipeline 1 must be on the same VPC\. They can be on the same or different subnets\.
+ The subnet for the channel endpoint in pipeline 0 and the channel endpoint in pipeline 1 must be different from each other, but the two subnets must be on the same VPC\.
+ There are no other requirements for subnet uniqueness in any of the VPCs or subnets that you identify\.

Your setup must observe these rules for Availability Zone:
+ The Availability Zones for the two channel endpoints must be different\. 
+ Within each pipeline, the endpoint of the VPC input and the channel endpoint must be in the same Availability Zone\. This rule exists because both these endpoints are inside the channel pipeline, and the pipeline can't start in one Availability Zone and end in another\.

  If the VPC input is already set up in the VPC, it is probably easiest to identify the Availability Zone of that subnet as the shared Availability Zone\. 

  If the VPC input isn't yet set up, make sure that the subnets are in the same Availability Zone\. 
+ Within each pipeline, each channel endpoint can be in the same Availability Zone as the destination \(or destinations\)\. Or it can be in a different Availability Zone\. If you choose to set up with different Availability Zones, you will incur outgoing data transfer charges\. For more information about pricing, see [https://aws.amazon.com/medialive/pricing/](https://aws.amazon.com/medialive/pricing/)\. 