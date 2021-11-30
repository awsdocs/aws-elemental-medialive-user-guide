# Assess audio content<a name="assess-uss-audio"></a>

Consult the following table for information about how to assess the audio source\. Read across each row\.

**Note**  
You don't need to perform any assessment of the audio being delivered over CDI or from an AWS Elemental Link device\. These sources are always acceptable to MediaLive\.


****  

| Information to obtain | Verify the following | 
| --- | --- | 
| The available audio codecs or formats\. | Make sure that at least one of the audio codecs is included in the list of audio codecs in [Supported codecs for inputs](inputs-supported-containers-and-codecs.md)\.  | 
| The available languages for each codec\. For example, English, French\. | Identify the languages that you would like to offer\. Determine which of these languages the content provider can provide\.  | 
| The available coding modes \(for example, 2\.0 and 5\.1\) for each codec\. |  Identify the audio coding modes that you prefer for each audio language\. Determine which of these coding modes the content provider can provide\. For more information, see the [section after this table](#coding)\.   | 
| Whether the audio characteristics change in the middle of the stream\.  |  For best results, verify that the audio characteristics of the source content don't change in the middle of the stream\. For example, the codec of the source should not change\. The coding mode should not change\. A language should not disappear\.  | 
| If the source content is HLS, whether the audio assets are in an audio rendition group or multiplexed with video\.  |  MediaLive can ingest audio assets that are in a separate rendition group or multiplexed into a single stream with the video\.  | 

**To decide on a coding mode**  
If multiple coding modes are available for the same language, decide which mode you want to use\. Follow these guidelines:
+ You can extract some languages in one codec and coding mode, and other languages in another codec and coding mode\. For example, you might want one or two languages available in 5\.1 coding mode, and want other languages in 2\.0 coding mode\. 
+ You can extract the same language more than once\. For example, you might want one language in both 5\.1 coding mode and coding mode 2\.0\.
+ When deciding which codec and coding mode to extract for a given language, consider the coding mode you want for that language in the output\. For each language, it is always easiest if the coding mode of the source content matches the coding mode of the output, because then you don't have to remix the audio in order to convert the coding mode\. MediaLive supports remix, but remixing is an advanced feature that requires a good understanding of audio\.

For example, in the output, you might want the one language to be in coding mode 5\.1\. You might want other languages to be available in coding mode 2\.0\.

Therefore you might choose to extract the following:
+ Spanish in Dolby Digital 5\.1
+ French and English in AAC 2\.0\.