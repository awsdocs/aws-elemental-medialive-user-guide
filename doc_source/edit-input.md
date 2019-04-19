# Editing an Input<a name="edit-input"></a>

The rules for editing an input are as follows:
+ You can attach a different input security group\. 
+ For an RTP input or an RTMP push input that isn't for a VPC, you can edit the fields in the input endpoint\.
+ For an RTP VPC input or an RTMP VPC push input, you can't edit the IP addresses input endpoint\. To change these addresses, you must delete the input and create it again\.
+ For a MediaConnect push input, you can edit the ARNs to refer to different MediaConnect flows\. The outputs for the former ARNs will be deleted in AWS Elemental MediaConnect, and new outputs \(with new IDs\) for the new ARNs will be created\. 
+ For a pull input, you can edit the fields in an input source\. 
+ You can't change the type of an input\. For example, if you set up an input as an RTMP push but it is actually an HLS input, delete the input and create it again\. 

There are constraints on performing these edits, as follows:
+ If an input is attached to a channel, you can edit the input only if the channel is idle\.
+ If an input is attached to a channel and an input security group, you can edit the input only if the channel is idle\.
+ If an input is not attached to a channel, you can edit it at any time, even if it is attached to an input security group\.

**To edit an input**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. Choose the name of the input, and then choose **Edit**\.

1. On the **Inputs** page, make the following changes as appropriate:
   + You can change the **Name**\.
   + You can't change the **Input type**\. If the input has the wrong type, delete it and create it over again\.
   + You can change the **Source **section \(applies only to "pull" inputs\)\. 
   + You can change the **Endpoint** section only on an RTP input or RTMP push input that isn't for a VPC\.
   + You can change the **Input security groups** section \(applies only to "push" inputs that aren't for a VPC\)\.
   + In the **Tags** section, you can add or delete tags\. To edit the value of an existing tag, delete the tag and add it again\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\.

1. Choose **Update**\.

   Wait for the input **State** to return to **In use** or **Idle** before performing another action with this input\.