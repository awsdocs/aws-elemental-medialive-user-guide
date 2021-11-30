# Supported codecs for inputs<a name="inputs-supported-containers-and-codecs"></a>

The following table lists the codecs that MediaLive supports for source content\.


| Container | Video codecs | Audio codecs | 
| --- | --- | --- | 
| CDISee [Characteristics of video and audio sources](inputs-video-audio-characteristics.md) for more information\. | Uncompressed video | PCM | 
| HLSSee [HLS inputs](#hls-inputs-anchor), after this table\. | H\.264 \(AVC\) |  AAC Dolby Digital Dolby Digital Plus  | 
| Link | Any codec that is included in a Link container is always supported by MediaLive | Up to four stereo pairs \(2\.0 audio\) | 
| MediaConnect |  H\.264 \(AVC\) HEVC \(H\.265\) MPEG\-2  |  AAC Dolby Digital Dolby Digital Plus MPEG Audio PCM  | 
| MP4 | H\.264 \(AVC\)HEVC \(H\.265\)MPEG\-2 | AAC | 
| Transport Stream \(TS\) file |  H\.264 \(AVC\) HEVC \(H\.265\) MPEG\-2  |  AAC Dolby Digital Dolby Digital Plus MPEG Audio PCM  | 
| RTMP | H\.264 \(AVC\) | AAC | 
| RTP |  H\.264 \(AVC\) HEVC \(H\.265\) MPEG\-2  |  AAC Dolby Digital Dolby Digital Plus MPEG Audio PCM  | 

**HLS inputs**

The audio and video assets can be multiplexed into a single stream or in a separate audio rendition group\. If you are using audio in a rendition group, the group can be selected by using the **Group ID** and **Name** that is in the **\#EXT\-X\-MEDIA** tag\.