# Audio rendition groups for HLS<a name="audio-renditions"></a>

You can set up an HLS output group to include an audio rendition group\. An audio rendition group is a set of MediaLive audio encodes \(for example, a set of languages\) that is associated with a video\. Audio rendition groups let the downstream client player select a video and then select from among several audio encodes that all apply to that video\.

Each audio encode in an audio rendition group is called an *audio rendition* or an *audio variant* or an *audio variant stream*\.

You can set up the HLS output group in one of these ways:
+ As a regular HLS output group, with video, audio \(in a rendition group\), and optional captions\.

  The video might be associated with only one audio rendition group, or it might be associated with several\. For example, the video might be associated with one group consisting of high\-bitrate audio and another group consisting of low\-bitrate audio\.

  Or one audio rendition group might be associated with several videos\. For example, the same audio rendition group might be associated with the high, medium, and low\-bitrate video offerings\.
+ As an audio\-only rendition group\.

  In this case, follow the steps in this procedure, but ignore steps for setting up video\.

**Note**  
The information in this section assumes that you are familiar with the general steps for creating a channel, as described in [Creating a channel from scratch](creating-channel-scratch.md)\.   
The key fields in the console that relate to this feature are under the **HLS Settings** field on the **Output settings** section of the **HLS output group** section on the **Create channel** page\. To review the step where you complete these fields, see [Procedure to create an HLS output group](hls-create-procedure.md)\. 

**Topics**
+ [About audio rendition groups](ARGs-about.md)
+ [Creating an output with an audio rendition group](ARG-create.md)
+ [Sample manifest](sample-manifest.md)