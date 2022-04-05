# Working with AWS Elemental Link devices<a name="feature-elink"></a>

AWS Elemental Link is a *hardware device* that connects a live video source, such as a camera or video production equipment, to MediaLive\. The AWS Elemental Link device connects to AWS over a secure connection that AWS manages\. After the hardware device is connected, it automatically appears in MediaLive as a MediaLive *device*\. You then create an *Elemental Link input* that uses this MediaLive device\. You can then use the input as you would use any input—you attach the input to a channel\. 

For information about purchasing an AWS Elemental Link device, see [Elemental Appliances and Software](https://console.aws.amazon.com/elemental-appliances-software/home#/linkhome)\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\link-parts.png)

To clarify the terminology:
+ AWS Elemental Link is a physical hardware device\. 
+ MediaLive device is the representation of AWS Elemental Link within MediaLive\. 
+ Elemental Link input is a type of input in MediaLive\.

The remainder of this section provides an overview of how you work with the AWS Elemental Link hardware, the MediaLive device, and the Elemental Link input\.

**Topics**
+ [Setting up AWS Elemental Link in MediaLive](#elink-setup-device)
+ [Using the AWS Elemental Link device as an input](#elink-using)
+ [Rules for devices, inputs, and channels](#rules-devices-link-inputs)

## Setting up AWS Elemental Link in MediaLive<a name="elink-setup-device"></a>

Read this section if you have the AWS Elemental Link hardware device in your possession\. You might be a regular user of MediaLive who wants to use the hardware device with MediaLive, or you might be someone who is responsible for setting up the device but is not a regular MediaLive user\.

**To deploy the hardware device**

1. To set up the AWS Elemental Link device and connect it to the internet, see the instructions included in the packaging\.

   The device is factory\-configured to connect to the AWS account and Region that you specified when you purchased the device\.

1. Set up permissions in AWS Identity and Access Management \(IAM\):
   + If you are a regular user of MediaLive, make sure that you or your administrator gives you permission to work with the MediaLive devices\. See [Step 1: Identify requirements for permissions for users](setup-user-step-1.md)\.
   + If you are not a regular MediaLive user, you or an administrator in your organization must create an IAM user for you, so that you can use the MediaLive console to manage MediaLive device or devices\. See [Creating a non\-administrator user ](iam-device-create-users.md)\.

1. If you need to transfer the device to a different AWS account, follow the steps in [Transferring a device](device-transfers.md)

## Using the AWS Elemental Link device as an input<a name="elink-using"></a>

Read this section if you are a MediaLive user who plans to create a channel that has an input from an AWS Elemental Link device\.

MediaLive and AWS Elemental Link work together as follows: 
+ As soon the hardware device has been set up \(as described in the previous section\), MediaLive automatically creates a MediaLive device\. This device [appears on the console](eml-devices.md) in the list of **Devices**\. 
+ To view the MediaLive devices attached to MediaLive in the current Region, see [Working with MediaLive devices](eml-devices.md)\.

  If you don't see a device that you are expecting, it might be in the process of being transferred to your AWS account\. You might need to [accept the incoming transfer](device-transfers.md)\.
+ You don't need to configure the MediaLive device, except to optionally throttle the delivery bitrate of the AWS Elemental Link device and to specify which of its ports to use\. 

  For more information on fine\-tuning the device, see [Working with MediaLive devices](eml-devices.md)\.
+ To use the device in a channel, you create an Elemental Link input in MediaLive, specifying the device as the source\. For more information, see [Identifying content in an AWS Elemental Link source](extract-contents-link.md) and [Setting up an AWS Elemental Link source](device-push-upstream.md)\.
+ When you are ready to use the Elemental Link input in a channel, you attach the input to a channel, in the same way as you would attach any input\. For information, see [Input settings—Video selector](input-video-selector.md)\.

  Typically, you perform this setup after the operator at the upstream system has powered on the AWS Elemental Link device, connected it to the internet, and started sending a video stream\. You wait to attach the input, in order to avoid charges for an idle input and for a running channel\.

## Rules for devices, inputs, and channels<a name="rules-devices-link-inputs"></a>
+ You can create up to four Elemental Link inputs from each MediaLive device\. You can then attach each input to a different channel\.

  When you set up inputs in this way, you are not replicating the MediaLive device\. There is still only one MediaLive device, but that device is the source for several separate inputs\.
+ You can attach up to two Elemental Link inputs to one channel\. Elemental Link inputs are push inputs, so each one counts towards your maximum number of push inputs in the channel\.
  + You can attach these two Elemental Link inputs to one standard channel in order to implement pipeline redundancy\.
  + You can include one or both of these Elemental Link inputs in a multiple\-input channel, as part of an [input switching workflow](scheduled-input-switching.md)\.