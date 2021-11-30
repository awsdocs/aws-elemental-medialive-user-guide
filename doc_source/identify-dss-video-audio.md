# Step 2: Identify the encode requirements for the output groups<a name="identify-dss-video-audio"></a>

After you have identified the output groups that you need to create, you must identify the requirements for the video and audio encodes that you will include in each output group\. The downstream system controls these requirements\.

Perform this work with the downstream system before you assess the [upstream system](evaluate-upstream-system.md)\. Decision making in a workflow starts with the downstream system, then works back to the upstream system\.

**Result of this procedure**

After you have performed this procedure, you will know what output groups you will create, and you will know which video and audio codecs those output groups can support\. Therefore, you should have output information that looks like this example\.


**Example**  

|  Output group   |  Downstream system  |  Video codecs supported by downstream system  | Audio codecs supported by downstream system | 
| --- | --- | --- | --- | 
|  HLS  |  MediaPackage  |  AVC  | AAC 2\.0, Dolby Digital Plus | 
| RTMP | social media site | AVC | AAC 2\.0 | 
| Archive | Amazon S3 | The downstream system doesn't dictate the codec—you choose the codec that you want\. | The downstream system doesn't dictate the codec—you choose the codec that you want\. | 

**To identify the video and audio codecs in each output group**

Perform this procedure on every output group that you identified\.

1. Obtain the following video information from your downstream system:
   + The video codec or codecs that they support\. 
   + The maximum bitrate and maximum resolution that they can support\.

1. Obtain the following audio information from your downstream system:
   + The supported audio codec or codecs\.
   + The supported audio coding modes \(for example, 2\.0\) in each codec\.
   + The maximum supported bitrate for audio\.
   + For an HLS or Microsoft Smooth output format, whether the downstream system requires that the audio is bundled in with the video or that each audio appears in its own rendition\. You will need this information when you organize the assets in the MediaLive outputs\.

1. Obtain the following captions information from your downstream system\.
   + The captions formats that they support\.

1. Verify the video\. Compare the video codecs that your downstream system requires to the video codecs that MediaLive supports for this output group\. See the tables in [Supported codecs for outputs](outputs-supported-containers-and-codecs.md)\. Make sure that at least one of the downstream system's offered codecs is supported\. 

1. Verify the audio\. Compare the audio codecs that your downstream system requires to the video codecs that MediaLive supports for this output group\. See the tables in [Supported codecs for outputs](outputs-supported-containers-and-codecs.md)\. Make sure that at least one of the downstream system's offered codecs is supported\. 

1. Skip assessment of the caption formats for now\. You will assess those requirements in [a later section](assess-uss-captions.md)\.

1. Make a note of the video codecs and audio codecs that you can produce for each output group\.

1. Decide whether you want to implement a trick\-play track\. For more information, see [Implementing a trick\-play track](trick-play-solutions.md)\.

   \.