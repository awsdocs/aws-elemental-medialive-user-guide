# Step 4: Set up key information<a name="getting-started-step4"></a>

The first step to creating a channel from scratch is to choose the IAM role that MediaLive will use to access the channel when the channel is running \(started\) and specify key characteristics of the input\. Now you are ready to start creating a channel\. The first step is to identify the input\. The channel contains the details that instruct MediaLive how to transcode \(decode and encode\) and package that input into specific outputs\.

The first step to creating a channel from scratch is to choose the IAM role that MediaLive will use to access the channel when the channel is running \(started\) and specify key characteristics of the input\.

**To specify key information for the channel**

1. On the MediaLive console, in the navigation pane, choose **Channels**\.

1. In the **Channels** section, choose **Create channel**\. 

1. In the **Channel and input details** pane, in **General info**, for **Channel name**, enter **Test channel**\.

1. For **IAM role**, choose **Create role from template** and choose **Create IAM role**\. The **Use existing role** list now shows the role **MediaLiveAccessRole**\.

1. Choose **Remember role**\.