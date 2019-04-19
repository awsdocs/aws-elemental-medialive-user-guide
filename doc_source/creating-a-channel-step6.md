# Step 7: Set Up the Video Encode<a name="creating-a-channel-step6"></a>

The output section for every type of output group contains a **Stream settings** section\. In this section, you create [encodes](channels.md#encode) for the video, audio \(if applicable\), and captions \(if applicable\) in the output and specify the details of how you want these assets encoded\. 

The following procedure describes how to set up a video encode and assumes that you have [created the output](creating-a-channel-step5.md) that will hold the video\. The fields for a video encode are identical for all output group types\. For example, the fields for video for an HLS group are identical to those for a UDP group\. 

**To set up the video encodes in most output types**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output \(or the first output\) where you want to set up a video encode\.

1. Choose the link for the video encode\. 

1. For **Codec settings**, choose the codec to use for this output\. More fields appear\. 

1. Complete each field as appropriate\. For details about a field, choose the **Info** link next to the field\. 

1. Continue setting up the [audio encodes](creating-a-channel-step7.md), video encodes, and [captions encodes](creating-a-channel-step8.md) for all outputs in all output groups\. When you finish with the encodes for all outputs, go to [save the channel](creating-a-channel-step9.md)\.

**To set up the video encodes in the Frame Capture output type**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output and choose the link for the video encode\.

1. Complete each field as appropriate\. For details about a field, choose the **Info** link next to the field\.

1. When you are ready, go to [save the channel](creating-a-channel-step9.md)\.

## Setting the Rate Control Mode<a name="video-encode-ratecontrol"></a>

This feature does not apply to the video in a Frame Capture output\.

The **Rate control** section in the **Video** section of each output on the console lets you control the quality and bitrate of the video\. 

When encoding visually complex video \(such as high\-motion sports events with brightly dressed crowds in the background\), there is always a trade\-off between high video quality and low bitrate\. Higher video quality requires higher bitrate\. There is less trade\-off with visually simple video such as cartoons\. 

AWS Elemental MediaLive offers several options that provide different balances of video quality versus bitrate\.

**To set the rate control mode and bitrate for the output**

1. On the **Stream settings** pane, for **Video**, for **Codec settings**, choose **H264**\.

1. In the **Rate Control** section, for **Rate control mode**, choose **QVBR** or **CBR** or **VBR**\. For information about choosing the best option, see the sections below\.
   + If you chose **QVBR**, complete **Max bitrate** and **Quality level**\. 
   + If you chose **VBR**, complete **Bitrate** \(average bitrate\) and **Max bitrate**\.
   + If you chose **CBR**, complete **Bitrate**\.

### Quality\-defined Variable Bitrate Mode \(QVBR\)<a name="video-encode-ratecontrol-qvbr"></a>

With quality\-defined variable bitrate mode \(QVBR\), you specify a maximum bitrate and a quality level\. Video quality will match the specified quality level except when it is constrained by the maximum bitrate; this constraint occurs when the video is very complex so that it is not possible to reach the quality level without exceeding the maximum bitrate\. 

We recommend this mode if you or your viewers pay for bandwidth, for example, if you are delivering to a CDN such as Amazon CloudFront or if your viewing users are on mobile networks\.

**Values to use:** When choosing QVBR, you should set the quality level and maximum bitrate for your most important viewing devices\. Set the buffer size to twice the maximum bitrate, and set the initial buffer to 90%\.


| Viewing Device | Quality Level | Max Bitrate | 
| --- | --- | --- | 
| Primary Screen  | 8 to 10 | 4,000,000 to 6,000,000 | 
| PC or Tablet | 7 | 1,500,000 to 3,000,000 | 
| Smartphone | 6 | 1,000,000 to 1,500,000 | 

**How it works:** The bitrate can change with each frame \(in order to obtain at least the specified quality\), but it can't exceed the maximum bitrate\. The encoder does not attempt to maintain an average bitrate\. It always reaches the maximum bitrate if that is necessary to obtain the specified quality\. On the other hand, if the quality can be obtained with lower bitrates, the encoder doesn't use a higher bitrate\.

### Variable Bitrate Mode \(VBR\)<a name="video-encode-ratecontrol-vbr"></a>

With variable bitrate mode \(VBR\), you specify an average bitrate and a maximum bitrate\. Video quality and bitrate vary, depending on the video complexity\.

Choose VBR instead of QVBR if you want to maintain a specific average bitrate over the duration of the channel\. If bitrate does not need to be constrained, then consider using QVBR\.

**Values to use:** When choosing VBR, you should try to assess the expected complexity of the video, and set a suitable average bitrate\. Set the maximum bitrate to accommodate expected spikes\. Set the buffer size to twice the maximum bitrate, and set the initial buffer to 90%\.

**How it works:** The bitrate can change with each frame \(in order to obtain the best quality\) but it can't exceed the specified maximum bitrate\. The encoder also ensures that as the channel progresses, the stream meets the specified average bitrate\. This mode is useful when you expect short spikes in the complexity of the video\. The encoder aims for the average bitrate but spikes to the maximum bitrate for a short time when necessary\. 

### Constant Bitrate Mode \(CBR\)<a name="video-encode-ratecontrol-cbr"></a>

With constant bitrate mode \(CBR\), you specify a bitrate\. Video quality varies, depending on the video complexity\.

Choose CBR only if you distribute your assets to devices that cannot handle variable bitrates\. 

But if it's acceptable for the bitrate to occasionally differ from a specified rate, then consider using VBR or QVBR\. Over the duration of the channel, you might obtain both a lower bitrate and better quality with VBR or QVBR\.

**Values to use:** When choosing CBR, set the bitrate to balance the video quality and the output bitrate\. Set the buffer size to twice the bitrate, and set the initial buffer to 90%\.

**How it works:** The output always matches the specified bitrate\. Sometimes that bitrate results in higher\-quality video, and sometimes it results in lower\-quality video\.