# Setting up for a MediaConnect source<a name="emx-upstream"></a>

This section describes how to create flows in AWS Elemental MediaConnect to deliver source content from the upstream system to AWS Elemental MediaLive, and how to create a MediaConnect input that connects the upstream system to MediaLive\. 

With a MediaConnect input, the service provider pushes content through MediaConnect to MediaLive\. \(From the point of view of MediaLive, the upstream system is MediaConnect\. The upstream system is not the service provider\.\) 

This diagram illustrates the final result of this setup\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\emx-push-uss-input.png)

To perform this setup, you must work with an AWS Elemental MediaConnect user\.

**Topics**
+ [Set up AWS Elemental MediaConnect](#setup-emx-flows)
+ [Create a MediaConnect input](#setup-input-emx)
+ [Result of this procedure](#setup-result-emx)

## Set up AWS Elemental MediaConnect<a name="setup-emx-flows"></a>

A MediaConnect user must set up AWS Elemental MediaConnect with flows to deliver source content to AWS Elemental MediaLive\.

**To set up flows for a standard channel**

1. Provide the MediaConnect user with this information:
   + Information about the provider of the source content\.
   + The AWS Region for the channel that you that will create\. The AWS Elemental MediaConnect flows and the MediaLive channel \(and input\) must be in the same Region\. 

     If the flows and the MediaLive channel aren't in the same Region, then the MediaConnect operator will have to set up a distribution to move the source content to the same Region as the MediaLive input\.

1. Discuss with the MediaConnect user whether you need new flows:
   + You need new flows if the source content doesn't yet have flows in MediaConnect\.
   + You can reuse existing flows so long as you follow these rules:
     + Each flow doesn't exceed its maximum output bandwidth\.
     + Each flow doesn't exceed its maximum number of outputs from the flow\. \(MediaLive automatically creates an output on each flow after you create the [MediaConnect input](input-create-push-mediaconnect.md)\.\)

1. If you decide you need new flows, ask the MediaConnect user to create two flows\. 
   +  They should assign flow names that are identical except for a suffix\. For example, **sports\_event\_A** and **sports\_event\_B**\. These suffixes will help you, the MediaLive user, to match the flows to the input pipelines in MediaLive\.
   + They should set up each flow in a different Availability Zone\. \(If the flows are in the same Availability Zone then you, the MediaLive user, won't be able to create the MediaLive inputs\.\)
   + They should speak to the service provider about the following:
     + To determine how to complete the source information for each flow\.
     + To make sure that the service provider delivers two sources\.
     + To make sure that the two sources have identical video resolution and bitrate\.
   + They should not create outputs or entitlements\.

1. Obtain the following information from the MediaConnect user:
   + The ARNs for the flows\. For example:

     `arn:aws:mediaconnect:us-west-1:111122223333:flow:1bgf67:sports_event_A`

     `arn:aws:mediaconnect:us-west-1:111122223333:flow:9pmlk76:sports_event_B`

     Note that the ARNs include the flow names as the last portion\. 

**To set up flows for a single\-pipeline channel**

1. Provide the MediaConnect user with this information:
   + Information about the provider of the source content\.
   + The AWS Region for the channel that you will create\. The AWS Elemental MediaConnect flow and the MediaLive channel \(and input\) must be in the same Region\. 

     If the flow and the MediaLive channel aren't in the same Region, then the MediaConnect operator will have to set up a distribution to move the source content to the same Region as the MediaLive input\.

1. Discuss with the MediaConnect user whether you need a new flow:
   + You need a new flow if the source content doesn't yet have a flow in MediaConnect\.
   + You can reuse an existing flow so long as you follow these rules:
     + The flow doesn't exceed its maximum output bandwidth\.
     + The flow doesn't exceed its maximum number of outputs from the flow\. \(MediaLive automatically creates an output on the flow after you create the [MediaConnect input](input-create-push-mediaconnect.md)\.\)

1. If you decide you need a new flow, ask the MediaConnect user to create one flow\. 
   + They should speak to the service provider to determine how to complete the source information for the flow\.
   + They should not create an output or entitlement\.

1. Obtain the ARN for the flow from the MediaConnect user\. For example:

   `arn:aws:mediaconnect:us-west-1:111122223333:flow:1bgf67:sports_event_A`

   Note that the ARN includes the flow name as the last portion\. 

## Create a MediaConnect input<a name="setup-input-emx"></a>

After MediaConnect is set up, you must create an input in order to connect AWS Elemental MediaLive to the MediaConnect flows\. A MediaLive user performs this step\.

For instructions on creating a MediaConnect input, see [Creating a MediaConnect push input](input-create-push-mediaconnect.md)\.

## Result of this procedure<a name="setup-result-emx"></a>

As a result of this setup, one or two MediaConnect flows exist\. Each flow has a source that the upstream system is pushing to\. Each flow also has one output for the use of MediaLive\. A MediaLive input exists that specifies the ARNs for those outputs\. 

The upstream system pushes the source content to the source on the AWS Elemental MediaConnect flow or flows\. The flows push the content to MediaLive\. At runtime of the channel, MediaLive reacts to the content that is being pushed and ingests it\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\emx-push-uss-input.png)