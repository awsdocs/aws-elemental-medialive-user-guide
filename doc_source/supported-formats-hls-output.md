# Formats Supported in an HLS Output or a MediaPackage Output<a name="supported-formats-hls-output"></a>

In this table, look up your input container and captions type\. Then read across to find the caption formats that are supported for an HLS output or MediaPackage output, when you have this input container and captions type\. 


| Source Caption Container | Source Caption Input | Supported Output Captions | 
| --- | --- | --- | 
| HLS Container | Embedded | Burn\-inEmbeddedWebVTT | 
|     | SCTE\-20 | Burn\-inEmbeddedWebVTT | 
| RTMP Container | Embedded | Burn\-inEmbeddedWebVTT | 
| MPEG2\-TS Container \(through the RTP or MediaConnect protocol\) | Embedded | Burn\-inEmbeddedWebVTT | 
|   | SCTE\-20 | Burn\-inEmbeddedWebVTT | 
|   | Teletext | Burn\-inWebVTT | 
|   | ARIB | None | 
|   | DVB\-Sub | Burn\-in | 
|   | SCTE\-27 | Burn\-in | 