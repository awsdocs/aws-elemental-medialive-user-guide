# Setting up an AWS Elemental Link source<a name="device-push-upstream"></a>

This section describes how to set up content that is being delivered from an AWS Elemental Link device, and how to create an Elemental Link input that connects the device to MediaLive\.

The AWS Elemental Link device *pushes* the content to MediaLive\. 

To perform this setup, you must work with an operator of the AWS Elemental Link device\.

**Topics**
+ [Obtain information](#setup-input-link-obtain-info)
+ [Create an Elemental Link input](#setup-uss-input-link)
+ [Result of this procedure](#setup-link-result)

## Obtain information<a name="setup-input-link-obtain-info"></a>

Obtain the following information from the operator of the AWS Elemental Link device:
+ The name of the device or devices that will provide your source\. For example:

  **hd\-re87jr7crey**

  You need two device names for a standard\-class input, or one device name for a single\-class input\. For information about input classes and their uses, see [Channel class and input class](class-channel-input.md)\.
+ The Region that the device is configured for, so that you can set MediaLive for that Region\. These rules apply:
  + Both devices must be in the same Region\.
  + The device, the input for that device, and the channel that uses the input must all be in the same Region\.

## Create an Elemental Link input<a name="setup-uss-input-link"></a>

You must create an Elemental Link input to connect the AWS Elemental Link device to MediaLive\. To create an Elemental Link input, see [Creating an Elemental Link input](input-create-link-device.md)\.

## Result of this procedure<a name="setup-link-result"></a>

As a result of this setup, an Elemental Link input exists that identifies the AWS Elemental Link device or devices that are connected to MediaLive\. There is no other setup for you to perform, because the AWS Elemental Link device is designed to work seamlessly with MediaLive\. 

At runtime of the channel, MediaLive reacts to and ingests the content that AWS Elemental Link is pushing\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\link-uss-input.png)