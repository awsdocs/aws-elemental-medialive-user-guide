# Setting up a CDI source<a name="cdi-push-vpc-upstream"></a>

This section describes how to set up content on an upstream system that is using AWS Cloud Digital Interface \(AWS CDI\) to deliver uncompressed content over your Amazon Virtual Private Cloud \(Amazon VPC\)\. It describes how to set up the source content on the upstream system, and how to create an input that connects the upstream system to AWS Elemental MediaLive\.

With a CDI source, the upstream system *pushes* the content to MediaLive\. 

This diagram illustrates the final result of this setup\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\cdi-vpc-uss-input.png)

To perform this setup, you must work with an Amazon VPC user, and with an operator at the upstream system\.

**Topics**
+ [Request setup on the VPC](#setup-vpc-cdi-vpc)
+ [Create a CDI input](#setup-input-cdi-vpc)
+ [Ensure correct setup on the upstream system](#setup-uss-cdi-vpc)
+ [Result of this procedure](#setup-result-cdi-vpc)

## Request setup on the VPC<a name="setup-vpc-cdi-vpc"></a>

An Amazon VPC user must set up the VPC, and identify subnets and security groups that the upstream system and MediaLive will use\. 

**To set up the VPC**

1. Provide the Amazon VPC user with the following guidelines\.
   + Guideline for the subnets – Request two subnets\. You need two subnets because a CDI input is always a [standard\-class input](class-channel-input.md), even if your channel is a single\-pipeline channel\. For information about input classes, see [Channel class and input class](class-channel-input.md)\.

     These rules apply:
     + The two subnets must be in different Availability Zones\.
     + Each subnet must have a private CIDR block \(a range of IP addresses\)\.
     + Each subnet must have at least two unused addresses in that block—one for the upstream system and one for the CDI input\.
     + Any other VPC\-based sources \(source B\) that you create for use in the same channel as this CDI source \(source A\) must be in subnets that are in the same Availability Zones as source A\. The two subnets of the source B can be different from the source A, but the Availability Zones of those two subnets must be the same as the Availability Zones of source A\.
   + Guideline for the security group – the security groups or groups for each subnet must follow these rules:
     + The combined inbound rules of the security groups must allow inbound traffic from the IP addresses of the upstream system that is in that subnet\.
     + The subnet must have an EFA\-enabled security group\. To create this type of security group and for information about its rules, see the [Amazon Elastic Compute Cloud User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/efa-start.html)\. 

1. After the Amazon VPC user has performed the setup, obtain the following information:
   + The ID of the VPC\. For example: `vpc-3f139646`
   + The IDs of the two subnets\. For example, one subnet might have this ID: `subnet-1122aabb`
   + The IDs of the security groups for the subnet or subnets\. For example: `sg-51530134`

## Create a CDI input<a name="setup-input-cdi-vpc"></a>

You must create a CDI input to connect the upstream system to MediaLive\. Use the information about the VPC that you obtained from the Amazon VPC user:
+ The ID of the VPC
+ The IDs of the two subnets
+ The IDs of the security groups for the subnet or subnets

For details on creating a CDI input, see [Creating a CDI push input in Amazon VPC](input-create-cdi-push.md)\.

## Ensure correct setup on the upstream system<a name="setup-uss-cdi-vpc"></a>

You must make sure that the operator at the upstream system sets up correctly with your VPC, and that they push content to the correct locations in MediaLive\.

**To set up for a standard channel**

If the planned channel is a [standard channel](plan-redundancy.md), you must ensure that the operator at the upstream system provides two sources\.

1. Provide the operator with this information:
   + The IDs of the VPC, two subnets, and the security groups that the Amazon VPC user gave you\.
   + The two endpoints \(URLs\) that MediaLive generated when you created the CDI input\. These endpoints are the addresses in the blue boxes in [the diagram after this procedure](#setup-result-cdi-vpc)\. These URLs each have a private IP address from the subnet range, and they specify port 5000\. For example: 

     `10.30.30.33:5000`

     `10.40.40.44:5000`

1. Make sure that the operator sets up properly for a standard channel\. They must do the following:
   + Set up two output interfaces\. Set up one upstream system with one output interface in one of the subnets, and set up the other upstream system with one output interface in the other subnet\. These interfaces are the addresses in the purple boxes in [the diagram after this procedure](#setup-result-cdi-vpc)\.
   + Make sure that the two content sources are identical in terms of video resolution and bitrate\.
   + Push to the correct URLs on MediaLive\. For example, they must push to:

     `10.30.30.33:5000`

     `10.40.40.44:5000`

**To set up for a single\-pipeline channel**

If the planned channel is a [single\-pipeline channel](plan-redundancy.md), you can request that the operator at the upstream system provides only one source, even though the CDI input is a standard\-class input\. The content from the upstream system will flow as follows:
+ There will be one upstream system that sends content to only one of the subnets in the VPC\. 
+ The content will flow from the VPC to one of the endpoints on the input\. The other endpoint will never be used\. 
+ MediaLive will ingest the single source content\.

1. Provide the operator with this information:
   + The IDs of the VPC, one of the subnets, and all of the security groups that the Amazon VPC user gave you\.
   + Only the first of the two endpoints \(URLs\) that MediaLive generated when you created the CDI input\. These endpoints are the addresses in the blue boxes in [the diagram after this procedure](#setup-result-cdi-vpc)\. The URL has a private IP address from the subnet range, and it specifies port 5000\. 

     `10.30.30.33:5000`

1. Make sure that the operator sets up properly for a single\-pipeline channel\. They must:
   + Set up one upstream system\.
   + Set up one output interfaces\. The interface is the address in one of the purple boxes in [the diagram after this procedure](#setup-result-cdi-vpc)\.
   + Push to the correct URL on MediaLive\. For example, they must push to:

     `10.30.30.33:5000`

## Result of this procedure<a name="setup-result-cdi-vpc"></a>

As a result of this setup, a CDI input exists that specifies one or two *endpoint* URLs\. These endpoints are elastic network interfaces \(ENIs\) on your VPC\. MediaLive has permission to use these ENIs for its inputs\. MediaLive has permission \(through the IAM trusted entity role\) to automatically manage the ENIs for its inputs\. The upstream system has permission, through the Amazon VPC security group, to push content to these endpoints\.

The upstream system or systems have been set up to push the source content to both endpoints \(if you are setting up a standard channel\) or to one endpoint \(if you are setting up a single\-pipeline channel\)\. At least one VPC security group has been associated with each subnet\. The CIDR block in each security group covers the two URLs that the upstream system pushes from, which ensures that MediaLive accepts the pushed content\.

Each output of the upstream system has an IP address in one of the specified subnets in your VPC\. The CDI input has two IP addresses, and each address is in one of those subnets\. In this way, the delivery of the source content from the upstream system to MediaLive takes place within the privacy of the VPC\. 

At runtime of the channel, MediaLive reacts to the content that is being pushed and ingests it\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\cdi-vpc-uss-input.png)