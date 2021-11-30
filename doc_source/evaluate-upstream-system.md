# Step 4: Assess the upstream system<a name="evaluate-upstream-system"></a>

As part of the planning of the MediaLive workflow, you must assess the upstream system that is the source of the content, to ensure that it is compatible with MediaLive\. Then you must assess the source content to ensure that it contains formats that MediaLive can ingest and that MediaLive can include in the outputs you want\. 

You obtain the *source content* from a *content provider*\. The source content is provided to you from an *upstream system* that the content provider controls\. Typically, you have already identified the content provider\. For more information about source content and upstream systems, see [How AWS Elemental MediaLive Works](how-medialive-works-channels.md)\.

**To assess the upstream system**

1. Speak to the content provider to obtain information about the upstream system\. You use this information to assess the ability of MediaLive to connect to the upstream system, and to assess the ability of MediaLive to use the source content from that upstream system\.

   For details about the information to obtain and assess, see the following sections:
   + [Assess source formats and packaging](uss-obtain-info.md)
   + [Assess video content](assess-uss-source.md)
   + [Assess audio content](assess-uss-audio.md)
   + [Assess captions](assess-uss-captions.md)

1. Make a note of the following three characteristics of the source stream\. You will need this information [when you set up the channel](input-specification.md):
   + The video codec
   + The resolution of the video—SD, HD, or UHD
   + The maximum input bitrate 

At the end of this step, you will know the following:
+ You will be confident that MediaLive can ingest the content\.
+ You will know what type of MediaLive input you will create to ingest the source content\.
+ You will have the information that you need to extract the video, audio, and captions from the source \(from the MediaLive input\)\.
+ You will have the basic information for setting up the channel to transcode the content\.