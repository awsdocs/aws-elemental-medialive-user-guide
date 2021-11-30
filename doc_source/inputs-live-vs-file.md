# Support for live and file inputs<a name="inputs-live-vs-file"></a>

The following table specifies whether an input type supports live streams or VOD assets\.


| MediaLive input type | Live stream supported? | VOD asset supported? | 
| --- | --- | --- | 
| CDI | Yes | No | 
| HLS from an HTTP or HTTPS server, or from MediaStore | YesMediaLive considers an HLS input to be a *live stream* if the **Buffer segments** field has a value from 3 to 10, inclusive\. \(To display this field in the **Channel** page, in **General input settings** for **Network input settings**, choose **Network input**\. For HLS input settings, choose **Hls input**\. The **Buffer segments **field appears\.\) | YesMediaLive considers the input to be a *VOD asset* if the **Buffer segments** field has a value of 11 or more, or is undefined \(empty\)\.  | 
| HLS from Amazon S3 | Yes, as defined in the previous row We don't recommend Amazon S3 as a source for a live stream\. | Yes, as defined in the previous row | 
| Link | Yes | No | 
| MediaConnect | Yes | No | 
| MP4 | No | Yes, with \.mp4 file extension only | 
| Transport Stream \(TS\) file | No | Yes, with \.ts and \.m2ts file extensions only | 
| RTMP Pull | Yes | Yes | 
| RTMP Push | Yes | No | 
| RTP | Yes | No | 