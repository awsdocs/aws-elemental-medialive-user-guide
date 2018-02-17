# Supported Input Types<a name="inputs-supported-containers"></a>

AWS Elemental MediaLive supports the following input sources\. 


| AWS Elemental MediaLive Option \(on the Create Input page\) | Use Case | Protocol | URI Format | Stream Input Supported | File Input Supported | 
| --- | --- | --- | --- | --- | --- | 
| RTP | Push a stream to a fixed endpoint on AWS Elemental MediaLive, using the RTP protocol\. | RTP |  rtp://<hostname>:5000/  | Yes |  | 
| RTMP Pull | Pull a stream from an external endpoint using the RTMP protocol\. | RTMP Pull | rtmp://<hostname>:1935/ | Yes |  | 
| RTMP Push | Push a stream to a fixed endpoint on AWS Elemental MediaLive, using the RTMP protocol\. For the application name, only “live” is supported\. | RTMP Push | <application name>/<stream name> | Yes |  | 
| HLS | Pull an HLS stream or file from an external endpoint using the HTTP protocol\. | HTTP  |  The path to the M3U8 manifest:  http://<web server>\[:port\]/path/file\.m3u8  | Yes | Yes | 
| HLS | Pull an HLS stream or file from an external endpoint using the HTTPS protocol\. | HTTPS |  The path to the M3U8 manifest:  https://<web server>/path/file\.m3u8  | Yes | Yes | 
| HLS | Pull an HLS stream or file from an Amazon S3 bucket\.  | Amazon S3 |  The path to the M3U8 manifest: s3://<web server>/path/file\.m3u8  | Yes | Yes | 
| HLS | Pull an HLS stream or file from an Amazon S3 bucket, using a secure connection\. | HTTPS |  The path to the M3U8 manifest: s3ssl://<web server>/path/file\.m3u8  | Yes | Yes | 
| HLS | Pull an HLS stream or file from an AWS Elemental MediaStore container, using a secure connection\. | HTTPS |  The path to the M3U8 manifest:  mediastoressl://eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com/premium/canada/mlaw\.m3u8   | Yes | Yes | 