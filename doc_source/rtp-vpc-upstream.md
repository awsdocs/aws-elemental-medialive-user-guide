# Setting up an RTP VPC source<a name="rtp-vpc-upstream"></a>

This section describes how to set up an upstream system that uses the RTP Push protocol to deliver source content from an upstream system that is in your Amazon Virtual Private Cloud \(Amazon VPC\)\. It describes how to set up the source content on the upstream system, and how to create an input that connects the upstream system to MediaLive\. 

With an RTP VPC source, the upstream system *pushes* the content to MediaLive\. 

This diagram illustrates the final result of this setup\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/rtp-vpc-uss-input.png)

To perform this setup, you must work with an Amazon VPC user, and with an operator at the upstream system\.

**Topics**
+ [Request setup on the VPC](#setup-vpc-rtp-vpc)
+ [Create an input for RTP push from Amazon VPC](#setup-input-rtp-vpc)
+ [Ensure correct setup on the upstream system](#setup-uss-rtp-vpc)
+ [Result of this procedure](#setup-rtp-vpc-result)

## Request setup on the VPC<a name="setup-vpc-rtp-vpc"></a>

An Amazon VPC user must set up the VPC, and identify subnets and security groups that the upstream system and MediaLive will use\. 

**To set up the VPC**

1. Provide the Amazon VPC user with the following guidelines\.
   + Guideline for the subnets – Request two subnets\.

     These rules apply:
     + You need two subnets because an RTP input is always a [standard\-class input](class-channel-input.md), even if your channel is a single\-pipeline channel\. For information about input classes, see [Channel class and input class](class-channel-input.md)\.
     + The two subnets must be in different Availability Zones\.
     + Each subnet must have a private CIDR block \(a range of IP addresses\)\.
     + Each subnet must have at least two unused addresses in that block—one for the upstream system and one for the RTP input\.
     + Any other VPC\-based sources \(source B\) that you create for use in the same channel as this RTP source \(source A\) must be in subnets that are in the same Availability Zones as source A\. The two subnets of the source B can be different from the source A, but the Availability Zones of those two subnets must be the same as the Availability Zones of source A\.
   + Guideline for the security group – The security group or groups for each subnet must follow these rules:
     + The combined rules of the security groups must allow inbound traffic from the IP addresses of the upstream system in that subnet\.
     + The combined rules of the security groups must allow outbound traffic to port 5000\. 

1. After the Amazon VPC user has performed the setup, obtain the following information:
   + The ID of the VPC\. For example: `vpc-3f139646`
   + The IDs of the two subnets\. For example, one subnet might have this ID: `subnet-1122aabb`
   + The IDs of the security groups for the subnets\. For example: `sg-51530134`

## Create an input for RTP push from Amazon VPC<a name="setup-input-rtp-vpc"></a>

You must create an input to connect AWS Elemental MediaLive to the content source on the upstream system\. Use the information that you obtained from the Amazon VPC user:
+ The ID of the VPC
+ The IDs of the two subnets
+ The IDs of the security groups for the subnet or subnets

For details on creating an RTP VPC input, see [Creating an RTP push input in Amazon VPC ](rtp-push-vpc-input.md)\.

## Ensure correct setup on the upstream system<a name="setup-uss-rtp-vpc"></a>

You must make sure that the upstream system sets up correctly with your VPC and pushes content to the correct locations in MediaLive\.

**To set up for a standard channel**

Follow this procedure if the MediaLive channel is a [standard channel](plan-redundancy.md)\.

1. Provide the operator with this information:
   + The IDs of the VPC, two subnets, and the security groups that the Amazon VPC user gave you\.
   + The two endpoints \(URLs\) that MediaLive generated when you created the RTP input\. These endpoints are the addresses in the blue boxes in [the diagram after this procedure](#setup-rtp-vpc-result)\. The URLs have private IP addresses and include port 5000\. For example: 

     `10.12.30.44:5000`

     `10.99.39.15:5000`

1. Make sure that the operator sets up properly for a standard channel\. They must:
   + Set up two output interfaces—one output interface in one of the subnets, and set up the other upstream system with one output interface in the other subnet\. These interfaces are the addresses in the purple boxes in [the diagram after this procedure](#setup-rtp-vpc-result)\.
   + Deliver two sources that are identical in terms of video resolution and bitrate\.
   + Push to the correct URLs on MediaLive\. For example, they must push to:

     `10.12.30.131:5000`

     `10.99.39.40:5000`
   + Send over RTP, not UDP\. The UDP protocol is not supported for an input into MediaLive\.

**To set up for a single\-pipeline channel**

Follow this procedure if the MediaLive channel is a [single\-pipeline channel](plan-redundancy.md)\.

1. Provide the operator with this information:
   + The IDs of the VPC, one subnet, and the security groups that the Amazon VPC user gave you\.
   + Only the first of the two endpoints \(URLs\) that MediaLive generated when you created the RTP input\. These endpoints are the addresses in the blue boxes in [the diagram after this procedure](#setup-rtp-vpc-result)\. The URL has a private IP address and includes port 5000\. For example: 

     `10.12.30.44:5000`

     `10.99.39.15:5000`

1. Make sure that the operator sets up properly for a standard channel\. They must:
   + Set up one output interface\. The interface is the address in one of the purple boxes in [the diagram after this procedure](#setup-rtp-vpc-result)\.
   + Push to the correct URL on MediaLive\. For example, they must push to:

     `10.12.30.131:5000`

     `10.99.39.40:5000`
   + Send over RTP, not UDP\. The UDP protocol is not supported for an input into MediaLive\.

## Result of this procedure<a name="setup-rtp-vpc-result"></a>

As a result of this setup, an RTP input exists that specifies one or two *endpoint* URLs\. These endpoints are elastic network interfaces \(ENIs\) on your VPC\. MediaLive has permission to use these ENIs for its inputs\. MediaLive has permission \(through the IAM trusted entity role\) to automatically manage the ENIs for its inputs\. The upstream system has permission, through the Amazon VPC security group, to push content to these endpoints\.

The upstream system or systems have been set up to push the source content to the two endpoints \(if you are setting up for a standard channel\) or to one endpoint \(if you are setting up for a single\-pipeline channel\)\. At least one VPC security group has been associated with each subnet\. The CIDR block in each security group covers the two URLs that the upstream system pushes from, which ensures that MediaLive accepts the pushed content\.

Each output of the upstream system has an IP address in one of the specified subnets in your VPC\. The RTP input has two IP addresses, and each address is in one of those subnets\. In this way, the delivery of the source content from the upstream system to MediaLive takes place within the privacy of the VPC\. 

At runtime of the channel, MediaLive reacts to the content that is being pushed and ingests it\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/rtp-vpc-uss-input.png)