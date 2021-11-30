# Streams section<a name="mediapackage-encode-packaging"></a>

The following fields relate to the encoding of the video, audio, and captions streams \(encodes\) in the output\. 
+ **Stream settings** section

For information about creating encodes, see the following sections:
+ [Step 6: Set up the video encode](creating-a-channel-step6.md)
+ [Step 7: Set up the audio encodes](creating-a-channel-step7.md)
+  [Step 8: Set up the captions encodes](creating-a-channel-step8.md)

## Packaging of video encodes and audio\-only encodes<a name="mediapackage-audio-rendition-handling"></a>

MediaLive handles the packaging of encodes within each output as follows:
+ If an output contains both video and audio \(and optionally captions\), the audio rendition is marked as **program audio**\.
+ If an output doesn't contain video, the audio rendition is marked as **audio only** and each audio encode is marked as **ALTERNATE\_AUDIO\_NOT\_AUTO\_SELECT**\.

## Setting the width and height of the video<a name="mediapackage-width-height"></a>

This section refers to the fields in **Stream settings**, **Video**\.

You must specify values in **Width** and **Height**\. The MediaPackage output group doesn't support leaving these fields blank to use the width and height from the source video\.

## Setting the aspect ratio of the video<a name="mediapackage-aspect-ratio"></a>

This section refers to the fields in **Stream settings**, **Video**, **Aspect ratio**\.

You must set **PAR control** to **SPECIFIED**\. The MediaPackage output group doesn't support setting the aspect ratio of the output to follow the source video\. When you choose **SPECIFIED**, you must complete **PAR numerator** and **PAR denominator**\. You can set the **AFD** fields as you want\.

## Setting the frame rate of the video<a name="mediapackage-framerate"></a>

This section refers to the fields in **Stream settings**, **Video**, **Frame rate**\.

You must set **Framerate control** to **SPECIFIED**\. The MediaPackage output group doesn't support setting the frame rate of the output to follow the source video\. When you choose **SPECIFIED**, you must complete **Framerate numerator** and **Framerate denominator**\. You can set the scan type as you want; it doesn't relate directly to the frame rate\.

## Setting up for GOPs and segments<a name="mediapackage-gop-segments"></a>

This section refers to the fields in **Stream settings**, **Video**, **GOP structure**\.

For the video, you must set the GOP size to ensure that the output from MediaLive has a segment size that is close to the segment size that you specify in MediaPackage\. MediaLive and MediaPackage work together to obtain a final segment size\. The logic is as follows:
+ In MediaLive you specify the **GOP size** and **GOP size units** fields\.
+ MediaLive calculates the GOP duration, taking into account the frame rate that you specify in the **Video** section of the **Output **page\.
+ In MediaPackage you specify the segment duration\. You always specify a whole number\. This segment duration is the *desired *minimum duration\. 
+ When MediaPackage receives the video from MediaLive, it determines how much it must adjust the segment duration to fit a whole number of GOPs into the segment\. The segment duration can only be adjusted up, never down\. This adjusted segment duration appears in the manifest that MediaPackage produces\.

**Example 1**

Assume that in MediaLive you set the GOP size to 60 frames\. You set the frame rate to 29\.97\. These two values result in a GOP duration of 2\.002 seconds\.

Assume that in MediaPackage you set the segment duration to 6 seconds\. This segment duration is the *desired* minimum duration\.

When MediaPackage receives the video from MediaLive, it determines how much it must adjust the segment duration to fit a whole number of GOPs into the segment\. In this case, the segment duration must be adjusted to 6\.006 seconds \(three GOPs, where each GOP is 2\.002 seconds long\)\. 

**Example 2**

Assume that in MediaLive, you set the GOP size to 90 frames\. You set the frame rate to 30\. These two values result in a GOP duration of 3 seconds\.

Assume that in MediaPackage you set the segment duration to 4 seconds\. This segment duration is the *desired* minimum duration\.

When MediaPackage receives the video from MediaLive, it determines how much it must adjust the segment duration to fit a whole number of GOPs into the segment\. In this case, the segment duration must be adjusted to 6 seconds \(two GOPs, where each GOP is 3 seconds long\)\.

## Other encode fields<a name="mediapackage-general-encode-settings"></a>

For information about the fields in each type of encode, see the following sections:
+ [Step 6: Set up the video encode](creating-a-channel-step6.md)
+ [Step 7: Set up the audio encodes](creating-a-channel-step7.md)
+  [Step 8: Set up the captions encodes](creating-a-channel-step8.md)