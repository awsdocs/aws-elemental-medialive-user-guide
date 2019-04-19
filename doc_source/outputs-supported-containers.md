# Supported Containers and Downstream Systems<a name="outputs-supported-containers"></a>

The following table lists the output formats and protocols that MediaLive supports\. 


| MediaLive Output Type \(Output Group\) | Use Case | Downstream System and Supported Protocol | Live Output Supported | VOD Output Supported | 
| --- | --- | --- | --- | --- | 
| Archive | Send transport stream \(TS\) files to an Amazon S3 bucket\. | Amazon S3 over a custom protocol | No | Yes | 
| Frame Capture | Send a series of JPEG files to an Amazon S3 bucket\. | Amazon S3 over a custom protocol | No | Yes | 
| HLS | Send an HLS stream to a server that supports HTTP PUT or WebDav\. | HTTP server | Yes | Yes, when the output group is set up for VOD mode | 
| HLS | Send an HLS stream to a server that supports HTTPS PUT or WebDav\. | HTTPS server | Yes | Yes, when the output group is set up for VOD mode | 
| HLS | Send an HLS stream to an Akamai CDN\. | Akamai CDN over HTTP or HTTPS | Yes | No | 
| HLS | Send an HLS stream to a MediaPackage channel using the HTTPS protocol\. | AWS Elemental MediaPackage over HTTPS | Yes | No | 
| HLS | Send an HLS stream to a container on MediaStore\. | AWS Elemental MediaStore with a custom protocol | Yes | Yes, when the output group is set up for VOD mode | 
| MediaPackage | Send an HLS stream to a MediaPackage channel\. | AWS Elemental MediaPackage over an HTTPS WebDav | Yes | No | 
| Microsoft Smooth | Send a stream to an origin server or CDN that supports Microsoft Smooth Streaming\. | A supported CDN over HTTP or HTTPS | Yes | No | 
| RTMP | Send a stream to a server that supports the RTMP protocol\. | RTMP server | Yes | No | 
| RTMP | Send a stream to a server that supports the RTMPS protocol\. | RTMPS server | Yes | No | 
| UDP | Send a transport stream \(TS\) to a server that supports UDP\. | UDP server | Yes | No | 