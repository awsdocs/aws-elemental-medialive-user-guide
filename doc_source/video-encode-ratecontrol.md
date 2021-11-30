# Setting the rate control mode<a name="video-encode-ratecontrol"></a>

This feature does not apply to the video in a Frame Capture output\.

You can configure the rate control mode when you set up the video as part of creating a channel\. This feature lets you control the quality and bitrate of the video\. 

**Note**  
The information in this section assumes that you are familiar with the general steps for creating a channel, as described in [Creating a channel from scratch](creating-channel-scratch.md), and specifically with [setting up the video](creating-a-channel-step6.md)\.

When encoding visually complex video \(such as high\-motion sports events with brightly dressed crowds in the background\), there is always a trade\-off between high video quality and low bitrate\. Higher video quality requires higher bitrate\. There is less trade\-off with visually simple video such as cartoons\. 

AWS Elemental MediaLive offers several options that provide different balances of video quality versus bitrate\.

**To set the rate control mode and bitrate for the output**

1. On the **Stream settings** pane, for **Video**, for **Codec settings**, choose **H264**\.

1. In the **Rate Control** section, for **Rate control mode**, choose **QVBR** or **CBR** or **VBR**\. The default mode is CBR\. For information about choosing the best option and about completing the other fields in the **Rate control mode** section, see the sections below\.

**Topics**
+ [Quality\-defined variable bitrate mode \(QVBR\)](#video-encode-ratecontrol-qvbr)
+ [Variable bitrate mode \(VBR\)](#video-encode-ratecontrol-vbr)
+ [Constant bitrate mode \(CBR\)](#video-encode-ratecontrol-cbr)

## Quality\-defined variable bitrate mode \(QVBR\)<a name="video-encode-ratecontrol-qvbr"></a>

With quality\-defined variable bitrate mode \(QVBR\), MediaLive aims for a specific quality and uses only the bitrate that it needs to reach that quality\. Video quality will match the specified quality except when the video is very complex\. In this case, when it's not possible to reach the desired quality without exceeding the maximum bitrate, MediaLive observes the maximum bitrate\. This means that the video doesn't achieve the desired quality\.

We recommend this mode if you or your viewers pay for bandwidth, for example, if you are delivering to a CDN such as Amazon CloudFront or if your viewing users are on mobile networks\.

With QVBR mode, you can specify a target quality, or you can let MediaLive determine the target quality\.

### Option 1: Setting a target quality<a name="qvbr-user-specifies-level"></a>

To set up in QVBR mode with a target quality that you specify, complete the fields as follows:
+ **Max bitrate**\. See the table that follows this list\.
+ **Quality level**\. See the table that follows this list\.
+ You must also set the Bitrate field\. Enter the same value as you enter in **Max bitrate**\. 

  This field has no effect on quality level in QVBR mode, but MediaLive does use it for calculating the output charges for this output\. For more information about charges, see [the MediaLive price list](https://aws.amazon.com/medialive/pricing/)\. If you leave **Bitrate** empty, MediaLive calculates charges using the value in the **Max input** bitrate in the [**Input specifications**](input-specification.md) section of the channel configuration\.
+ Set **Buffer size** to twice the maximum bitrate\.
+ Set **Buffer fill percentage** to 90%\.
+ Ignore the other fields in this section\. They aren't used for QVBR\.

**Values to use:** Set the **Max bitrate** and **Quality level** for your most important viewing devices\. See the following table for suggestions\.


| Viewing Device | Quality Level | Max Bitrate | 
| --- | --- | --- | 
| Primary Screen  | 8 to 10 | 4,000,000 to 6,000,000 | 
| PC or Tablet | 7 | 1,500,000 to 3,000,000 | 
| Smartphone | 6 | 1,000,000 to 1,500,000 | 

**How it works:** The bitrate can change with each frame \(in order to obtain at least the specified quality\), but it can't exceed the maximum bitrate\. The encoder does not attempt to maintain an average bitrate\. It always reaches the maximum bitrate if that is necessary to obtain the specified quality\. On the other hand, if the quality can be obtained with lower bitrates, the encoder doesn't use a higher bitrate\.

### Option 2: Letting MediaLive determine the quality level<a name="qvbr-auto-level"></a>

To set up in QVBR mode with a target quality that MediaLive determines, complete the fields as follows:
+ Leave the **QVBR quality level** field empty\.
+ In **Max bitrate**, enter the maximum rate you want the output to use\. 
+ You must also set the Bitrate field\. Enter the same value as you enter in **Max bitrate**\. 

  This field has no effect on quality level in QVBR mode, but MediaLive does use it for calculating the output charges for this output\. For more information about charges, see [the MediaLive price list](https://aws.amazon.com/medialive/pricing/)\. If you leave **Bitrate** empty, MediaLive calculates charges using the value in the **Max input** bitrate in the [**Input specifications**](input-specification.md) section of the channel configuration\.
+ Set **Buffer size** to twice the maximum bitrate\.
+ Set **Buffer fill percentage** to 90%\.

**How it works:** You don't specify a target quality\. Instead, MediaLive infers the quality you want based on the following fields you completed:
+ The output video resolution \(the values in the **Height** and **Width** fields that are also in this Video section\)\. 
+ The maximum bitrate\. 

The bitrate can change with each frame \(in order to obtain at least the quality that MediaLive has identified\), but it can't exceed the maximum bitrate\. The encoder does not attempt to maintain an average bitrate\. It always reaches the maximum bitrate if that is necessary to obtain the identified quality\. On the other hand, if the quality can be obtained with lower bitrates, the encoder doesn't use a higher bitrate\.

## Variable bitrate mode \(VBR\)<a name="video-encode-ratecontrol-vbr"></a>

With variable bitrate mode \(VBR\), you specify an average bitrate and a maximum bitrate\. Video quality and bitrate vary, depending on the video complexity\.

Choose VBR instead of QVBR if you want to maintain a specific average bitrate over the duration of the channel\. If bitrate does not need to be constrained, then consider using QVBR\.

To set up VBR mode, complete the fields as follows:
+ **Bitrate** \(average bitrate\)\. Try to assess the expected complexity of the video, and set a suitable average bitrate\.

  If you leave **Bitrate **empty, MediaLive sets the average bitrate to 5 Mbps\. 

  The value you enter in **Bitrate** also affects the output charges for this output\. If you leave **Bitrate** empty, MediaLive calculates charges using the value in the **Max input** bitrate in the [**Input specifications**](input-specification.md) section of the channel configuration\. For more information about charges, see [the MediaLive price list](https://aws.amazon.com/medialive/pricing/)\. 
+ Set the **Max bitrate** to accommodate expected spikes\.
+ Set **Buffer size** to twice the maximum bitrate\.
+ Set **Buffer fill percentage** to 90%\.
+ Ignore the other fields in this section\. They aren't used for VBR\.

**How it works:** The bitrate can change with each frame \(in order to obtain the best quality\) but it can't exceed the specified maximum bitrate\. The encoder also ensures that as the channel progresses, the stream meets the specified average bitrate\. This mode is useful when you expect short spikes in the complexity of the video\. The encoder aims for the average bitrate but spikes to the maximum bitrate for a short time when necessary\. 

## Constant bitrate mode \(CBR\)<a name="video-encode-ratecontrol-cbr"></a>

With constant bitrate mode \(CBR\), you specify a bitrate\. Video quality varies, depending on the video complexity\.

Choose CBR only if you distribute your assets to devices that cannot handle variable bitrates\. 

But if it's acceptable for the bitrate to occasionally differ from a specified rate, then consider using VBR or QVBR\. Over the duration of the channel, you might obtain both a lower bitrate and better quality with VBR or QVBR\.

To set up CBR mode, complete the fields as follows:
+ **Bitrate**\. Set the **Bitrate** to balance the video quality and the output bitrate\. If you leave this field empty, MediaLive sets the bitrate to 5 Mbps\.

  The value you enter in **Bitrate** also affects the output charges for this output\. If you leave **Bitrate** empty, MediaLive calculates charges using the value in the **Max input** bitrate in the [**Input specifications**](input-specification.md) section of the channel configuration\. For more information about charges, see [the MediaLive price list](https://aws.amazon.com/medialive/pricing/)\. 
+ Set **Buffer size** to twice the bitrate\.
+ Set **Buffer fill percentage** to 90%\.
+ Ignore the other fields in this section\. They aren't used for CBR\.

**How it works:** The output always matches the specified bitrate\. Sometimes that bitrate results in higher\-quality video, and sometimes it results in lower\-quality video\.