# Formats Supported in an MPEG2\-TS File Output or MPEG2\-UDP Streaming Output<a name="supported-formats-ts-output"></a>

In this table, look up your input container and captions type\. Then read across to find the caption formats that are supported for an MPEG2\-TS or MPEG2\-UDP output, when you have this input container and captions type\. 


| Source Caption Container | Source Caption Input | Supported Output Captions | 
| --- | --- | --- | 
| HLS Container | Embedded | Burn\-inDVB\-SubEmbeddedEmbedded\+SCTE\-20SCTE\-20\+Embedded | 
|   | SCTE\-20 | Burn\-inDVB\-SubEmbeddedEmbedded\+SCTE\-20SCTE\-20\+Embedded | 
| RTMP Container | Embedded | Burn\-inDVB\-SubEmbeddedEmbedded\+SCTE\-20SCTE\-20\+Embedded | 
| MPEG2\-TS Container \(through the RTP or MediaConnect protocol\) | Embedded | Burn\-inDVB\-SubEmbeddedEmbedded\+SCTE\-20SCTE\-20\+Embedded | 
|   | SCTE\-20 | Burn\-inDVB\-SubEmbeddedEmbedded\+SCTE\-20SCTE\-20\+Embedded | 
|   | Teletext | Burn\-inDVB\-SubTeletext | 
|   | ARIB | ARIB | 
|   | DVB\-Sub | Burn\-inDVB\-Sub | 
|   | SCTE\-27 | Burn\-inDVB\-SubSCTE\-27 | 