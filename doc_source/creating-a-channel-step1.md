# Step 1: Complete the Channel and Input Details<a name="creating-a-channel-step1"></a>

The first step to creating a channel from scratch is to choose the IAM role that AWS Elemental MediaLive will use to access the channel when the channel is running \(started\) and specify key characteristics of the input\.

**To provide channel and input details**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/s3/)\.

1. Before creating a channel, make sure that you have [created the input](creating-input.md) that you will attach to the channel\.

1. On the MediaLive home page, choose **Create channel**, and in the navigation pane, choose **Channels**\. 

   If you've created a channel before, you won't see the home page\. In that case, in the MediaLive navigation pane, choose **Channels**, and then choose **Create channel**\.

1. On the **Create channel** page, choose **Channel and input details**\.

1. In the **General info** section, do the following:
   + For **Channel name**, enter a name for your channel\. 
   + Complete **IAM role**\. See [IAM Role and ARN](role-and-remember-arn.md)\. 

1. For information about the **Channel template** section, see [Creating a Channel from a Template or by Cloning](creating-channel-template-clone.md)\.

1. In the **Channel class** section, choose the class\. See [Channel Class](channel-class.md)\.

1. In the **Input specifications** section, complete the fields to match your input\. See [Input Specifications Settings](input-specification.md)\.

1. In the **Tags **section, create tags if you want to associate tags with this channel\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\.

1. When ready, go to the [next step](creating-a-channel-step2.md)\.