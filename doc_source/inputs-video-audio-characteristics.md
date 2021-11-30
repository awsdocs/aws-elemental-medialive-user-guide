# Characteristics of video and audio sources<a name="inputs-video-audio-characteristics"></a>

**Orientation**

MediaLive only ingests landscape video\. If a video source is configured as portrait, MediaLive will ingest it but will rotate it to landscape\.

**Input frame rate**

MediaLive only supports constant frame rate \(CFR\) inputs\. It does not support variable frame rates \(VFR\)\.

**Other characteristics**


| Container | Video characteristics | Audio characteristics | 
| --- | --- | --- | 
| CDI |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/inputs-video-audio-characteristics.html)  |  24\-bit Big\-Endian PCM Mono \(1\.0\), Dual mono \(2\.0\), Stereo \(2\.0\), 5\.1, 7\.1 222, SGRP 48kHz, 96 kHz  | 