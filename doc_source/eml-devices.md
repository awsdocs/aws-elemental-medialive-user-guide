# Working with MediaLive devices<a name="eml-devices"></a>

A MediaLive *device* is the representation within MediaLive, of an AWS Elemental Link *hardware device* that's connected to MediaLive\. Use MediaLive device to manage the AWS Elemental Link hardware device that's connected to MediaLive\. You can fine\-tune the setup of the AWS Elemental Link hardware, transfer use of the device to another AWS account, or accept a device that is being transferred to you\.

**About MediaLive devices**  
The AWS Elemental Link hardware that's associated with the MediaLive device is the upstream system that provides the source to MediaLive\. The input type associated with the MediaLive device is an Elemental Link input\. AWS Elemental Link can stream content to any MediaLive channel\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\link-parts.png)

To clarify the terminology:
+ AWS Elemental Link is a physical hardware device\. For documentation for the hardware device, see [AWS Elemental Link](http://aws.amazon.com/https://aws.amazon.com//medialive/features/link)\.
+ MediaLive device is the representation of AWS Elemental Link within MediaLive\. This section describes how to work with the MediaLive device\.
+ Elemental Link input is a type of input in MediaLive\. For information about working with an Elemental Link input, see [Setting up an AWS Elemental Link source](device-push-upstream.md)\.

The AWS Elemental Link hardware is connected via the internet to MediaLive in a specific Region in your AWS account\. You don't need to configure MediaLive for AWS Elemental Link hardware\. Instead, the AWS Elemental Link hardware automatically connects itself to your AWS account, and automatically becomes visible to MediaLive\.

You set up to use the content from a specific AWS Elemental Link hardware by creating an input that uses the MediaLive device that corresponds to that hardware device\. You can then work with the input in MediaLive as you would work with any input\. For more information, see [Working with AWS Elemental Link devices](feature-elink.md)\.

**Topics**
+ [Creating a MediaLive device](device-create.md)
+ [Editing or viewing details for a MediaLive device](device-edit.md)
+ [Transferring a device](device-transfers.md)
+ [Viewing the status of a MediaLive device](device-status.md)
+ [Deleting a MediaLive device](device-delete.md)