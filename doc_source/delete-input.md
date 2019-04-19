# Deleting an Input<a name="delete-input"></a>

If an input is not attached to a channel, you can delete it, even if it is attached to an input security group\.

**Note**  
If the input is attached to a channel, you can't delete the input\. This rule exists to ensure that you don't remove an input from a channel and therefore make the channel unusable\.

When you delete an input, the attached input security group \(if any\) is *not* deleted\.

**To delete an input**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, find the input that you want to delete, and then look at the **State** column\. 

1. If the state is **Detached**, then choose **Delete**\. If the state is **Attached** and you want to delete both the input and its channel, then delete the channel first\. For more information, see [Deleting a Channel](editing-deleting-channel.md#deleting-a-channel)\.

   If the input is a MediaConnect push input, the corresponding outputs in AWS Elemental MediaConnect are automatically deleted; you don't have to delete the outputs\.

   If the input is an RTP VPC input or an RTMP VPC push input, the elastic network interfaces of the endpoints are deleted and the IPv4 addresses in the subnet are released for use by another resource\. You don't have to delete the network interfaces\.