# Step 1: Complete the channel details<a name="creating-a-channel-step1"></a>

The first step to creating a channel from scratch is to choose the IAM role that AWS Elemental MediaLive will use to access the channel when the channel is running \(started\) and specify key characteristics of the input\.

**To provide channel and input details**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. Before creating a channel, make sure that you have [created the input](creating-input.md) that you will attach to the channel\.

1. On the MediaLive home page, choose **Create channel**, and in the navigation pane, choose **Channels**\. 

   If you've created a channel before, you won't see the home page\. In that case, in the MediaLive navigation pane, choose **Channels**, and then choose **Create channel**\.

1. On the **Create channel** page, choose **Channel and input details**\.

1. Complete the sections:
   + In **General info**, for **Channel name**, type a name for your channel\. 
   + In **General info**, complete **IAM role**\. See [IAM role and ARN](role-and-remember-arn.md)\. 
   + For information about the **Channel template** section, see [Creating a channel from a template or by cloning](creating-channel-template-clone.md)\.
   + In **Channel class**, choose the class\. See [Channel class](channel-class.md)\.
   + In **Input specifications**, complete the fields to match your input\. See [Input specifications settings](input-specification.md)\.
   + In the **Tags **section, create tags if you want to associate tags with this channel\. For more information, see [Tagging AWS Elemental MediaLive resources](tagging.md)\.

1. When ready, go to the [next step](creating-a-channel-step2.md)\.