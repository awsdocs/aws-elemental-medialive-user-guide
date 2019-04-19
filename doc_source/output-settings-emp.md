# Settings for a MediaPackage Output<a name="output-settings-emp"></a>

In the **Output** page for a MediaPackage output group, you provide information about the video, audio, and captions encodes to create in the output\.

## Output Settings Section<a name="emp-output-section"></a>

There are no fields in the **Output** page for a MediaPackage output group\.

MediaLive automatically sets up the output as follows:
+ The output name or names are automatically set to `Output n`, where n is an integer starting at 1\. 
+ The name modifier for each output is automatically set to match the output name\.
+ Passthrough of SCTE\-35 messages is enabled\. For information about SCTE\-35 handling in a MediaPackage output, see [SCTE\-35 Message Processing](scte-35-message-processing.md)\.
+ ID3 metadata is enabled\. For information about ID3 handling in a MediaPackage output, see [Working with ID3 Metadata](id3-metadata.md)\.
+ The PAT interval is set to 0, which means a single PAT is inserted at the beginning of each segment\.
+ The PMT interval is set to 0, which means a single PMT is inserted at the beginning of each segment\.

## Streams Section<a name="emp-encode-packaging"></a>

In **Stream settings**, decide if you need to create more encodes for this output, based on the [workflow that you planned](planning-the-channel.md)\. By default, each output is set up with one video encode and one audio encode\. Choose the appropriate **Add** button or **Delete** button to set up the output with the encodes—video, audio, and captions—that you planned for this output\.

For example, in one output you might want one video asset and two audio assets, in another output you might want one captions asset for French captions, and in a third output you might want one captions asset for Spanish captions\. For information about why you would set up like this \(for example, with an output that contains only one captions asset\), see [Examples of Channel Designs](examples-channel-design.md)\.

### Packaging of Video Encodes and Audio\-only Encodes<a name="emp-audio-rendition-handling"></a>

MediaLive handles the packaging of encodes within each output as follows:
+ If an output contains both video and audio \(and optionally captions\), the audio rendition is marked as "program audio"\.
+ If an output doesn't contain video, the audio rendition is marked as "audio only" and each audio encode is marked as `ALTERNATE_AUDIO_NOT_AUTO_SELECT`\.

### Setting the Width and Height of the Video<a name="emp-width-height"></a>

This section refers to the fields in **Stream settings**, **Video**\.

You must specify values in **Width** and **Height**\. The MediaPackage output group doesn't support leaving this fields blank in order to use the width and height from the source video\.

### Setting the Aspect Ratio of the Video<a name="emp-aspect-ratio"></a>

This section refers to the fields in **Stream settings**, **Video**, **Aspect ratio**\.

You must set **PAR control** to **SPECIFIED**\. The MediaPackage output group doesn't support setting the aspect ratio of the output to follow the source video\. When you choose **SPECIFIED**, you must complete **PAR numerator** and **PAR denominator**\. You can set the AFD fields as you want\.

### Setting the Frame Rate of the Video<a name="emp-framerate"></a>

This section refers to the fields in **Stream settings**, **Video**, **Frame rate**\.

You must set **Framerate control** to **SPECIFIED**\. The MediaPackage output group doesn't support setting the frame rate of the output to follow the source video\. When you choose **SPECIFIED**, you must complete **Framerate numerator** and **Framerate denominator**\. You can set the scan type as you want; it doesn't relate directly to the frame rate\.

### Setting Up for GOPs and Segments<a name="emp-gop-segments"></a>

This section refers to the fields in **Stream settings**, **Video**, **GOP structure**\.

For the video, you must set the GOP size to ensure that the output from AWS Elemental MediaPackage has a segment size that is close to the segment size that you specify in AWS Elemental MediaPackage\. MediaLive and AWS Elemental MediaPackage work together to obtain a final segment size\. The logic is as follows:
+ In MediaLive, you specify the **GOP size** and **GOP size units** fields\.
+ MediaLive calculates the GOP duration, taking into account the frame rate that you specify in the **Video** section of the **Output **page\.
+ In AWS Elemental MediaPackage, you specify the segment duration\. You always specify a whole number\. This segment duration is the *desired *minimum duration\. 
+ When MediaPackage receives the video from MediaLive, it determines how much it must adjust the segment duration to fit a whole number of GOPs into the segment\. The segment duration can only be adjusted up, never down\. This adjusted segment duration appears in the manifest that AWS Elemental MediaPackage produces\.

Example 1:

Assume that in MediaLive, you set the GOP size to 60 frames\. You set the frame rate to 29\.97\. These two values result in a GOP duration of 2\.002 seconds\.

Assume that in MediaPackage, you set the segment duration to 6 seconds\. This segment duration is the *desired* minimum duration\.

When MediaPackage receives the video from MediaLive, it determines how much it must adjust the segment duration to fit a whole number of GOPs into the segment\. In this case, the segment duration must be adjusted to 6\.006 seconds \(3 GOPs, where each GOP is 2\.002 seconds long\)\. 

Example 2:

Assume that in MediaLive, you set the GOP size to 90 frames\. You set the frame rate to 30\. These two values result in a GOP duration of 3 seconds\.

Assume that in MediaPackage, you set the segment duration to 4 seconds\. This segment duration is the *desired* minimum duration\.

When MediaPackage receives the video from MediaLive, it determines how much it must adjust the segment duration to fit a whole number of GOPs into the segment\. In this case, the segment duration must be adjusted to 6 seconds \(2 GOPs, where each GOP is 3 seconds long\)\.

### Other Encode Fields<a name="emp-general-encode-settings"></a>

For information about the fields in each type of encode, see [Step 7: Set Up the Video Encode](creating-a-channel-step6.md), [Step 8: Set Up the Audio Encodes](creating-a-channel-step7.md), and [Step 9: Set up the Captions Encodes](creating-a-channel-step8.md)\. 