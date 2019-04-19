# Step 2: Attach Inputs to the Channel<a name="creating-a-channel-step2"></a>

You must choose the input or inputs to attach to the channel, and then configure how AWS Elemental MediaLive will handle this input\. 

You can attach multiple inputs to the channel\. For detailed information about setting up a channel with more than one input, see [Input Switching in AWS Elemental MediaLive](scheduled-input-switching.md)\. There are specific rules about the number and type \(push versus pull, for example\) of inputs that you can attach to one channel\.

**To attach one input**

1. On the **Create channel** page, for **Input attachments**, choose **Add**\.

1. On the **Attach input** page, for **Input**, choose an existing input\. More ﬁelds appear\. 

   Complete the ﬁelds that apply to your input\. See the following sections:
   + [Channel Input—HLS Pull Input](input-hls-pull.md)
   + [Channel Input—MediaConnect Push Input](input-mediaconnect-push.md)
   + [Channel Input—MP4 Pull Input](input-mp4-pull.md)
   + [Channel Input—RTMP Push Input](input-rtmp-push.md)
   +  [Channel Input—RTMP Pull Input](input-rtmp-pull.md) 
   + [Channel Input—RTP Push Input](input-rtp-push.md) 

1. For **Attachment name**, enter a name for the attachment\. The default name is the name of the input itself\. You will need to change this default if you have already attached this input to the channel because names must be unique in the channel\.

1. Choose **Confirm**\. The **Input attachment** section closes, and the **General input settings** section appears\.

1. For information about completing the fields in the **General input settings** section, go to the [next step](creating-a-channel-step3.md)\.

**Topics**
+ [Channel Input—HLS Pull Input](input-hls-pull.md)
+ [Channel Input—MediaConnect Push Input](input-mediaconnect-push.md)
+ [Channel Input—MP4 Pull Input](input-mp4-pull.md)
+ [Channel Input—RTMP Push Input](input-rtmp-push.md)
+ [Channel Input—RTMP Pull Input](input-rtmp-pull.md)
+ [Channel Input—RTP Push Input](input-rtp-push.md)