# Formats Supported in an RTMP Output<a name="supported-formats-rtmp-output"></a>

In this table, look up your input container and captions type\. Then read across to find the caption formats that are supported for an RTMP output, when you have this input container and captions type\. 


| Source Caption Container | Source Caption Input | Supported Output Captions | 
| --- | --- | --- | 
| HLS Container | Embedded | Burn\-inRTMP CaptionInfo | 
|   | SCTE\-20 | None | 
| RTMP Container | Embedded | Burn\-inRTMP CaptionInfo | 
| MPEG2\-TS Container \(through the RTP or MediaConnect protocol\) | Embedded | Burn\-inRTMP CaptionInfo | 
|   | SCTE\-20 | None | 
|   | ARIB | None | 
|   | DVB\-Sub | Burn\-in | 
|   | SCTE\-27 | Burn\-in | 