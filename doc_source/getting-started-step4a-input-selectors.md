# Step 6: Set up input video, audio, captions<a name="getting-started-step4a-input-selectors"></a>

You can create "selectors" to identify the specific video, audio, and captions that you want to extract from the input\. 

In this tutorial, you don't create a video selector\. Instead, when the channel starts, MediaLive will automatically select the video \(or the first video\) in the input\. You also don't create a captions selector Typically, you include captions in the channel configuration, but in this tutorial we omit them\.

You do create an audio selector\.

**To identify the content to extract**

1. On the **Create channel** page, in the **Input settings** pane, for **Audio** selectors, choose **Add audio selectors**\.

1. For **Audio selector name**, enter **My audio source**\.

   Ignore the **Selector settings** field\. You don't need to specify the PID or language\. When the channel starts, MediaLive will automatically select the first audio, which is acceptable for this tutorial\.

1. For all other fields in this pane, keep the default values\. 