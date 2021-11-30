# Assess video content<a name="assess-uss-source"></a>

Consult the following table for information about how to assess video source\. Read across each row\.

**Note**  
You don't need to perform any assessment of the video being delivered over CDI or from an AWS Elemental Link device\. These sources are always acceptable to MediaLive\.


****  

| Information to obtain | Verify the following | 
| --- | --- | 
| The available video codecs or formats\. | Make sure that at least one of the video codecs is included in the list of video codecs for the package format\. See [Supported codecs for inputs](inputs-supported-containers-and-codecs.md)\. If the content is available in more than one supported codec, decide which single video codec you want to use\. You can extract only one video asset from the source content\. | 
| The available resolutions\.  | MediaLive supports only landscape mode\. | 
| The maximum expected bitrate\. | Make sure that the bandwidth between the upstream system and MediaLive is sufficient to handle the anticipated maximum bitrate of the source content\.If you are setting up standard channels \(to implement [pipeline redundancy](plan-redundancy.md)\), make sure that the bandwidth is double the anticipated maximum bitrate because there are two pipelines\. | 
| Whether the video characteristics change in the middle of the stream\.  | For best results, verify that the video characteristics of the video source don't change in the middle of the stream\. For example, the codec should not change\. The frame rate should not change\. | 