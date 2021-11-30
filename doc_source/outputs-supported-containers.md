# Supported containers and downstream systems<a name="outputs-supported-containers"></a>

The following table lists the output formats and protocols that MediaLive supports\. 


| MediaLive output type \(output group\) | Use case | Downstream system and supported protocol | Live output supported | VOD output supported | 
| --- | --- | --- | --- | --- | 
| Archive | Send transport stream \(TS\) files to an Amazon S3 bucket\. See [Amazon S3 Bucket Names](#s3-bucket-rule-anchor), after this table\. | Amazon S3, over a custom protocol | No | Yes\. A channel can contain only one archive output group\. | 
| Frame Capture | Send a series of JPEG files to an Amazon S3 bucket\. See [Amazon S3 Bucket Names](#s3-bucket-rule-anchor), after this table\. | Amazon S3, over a custom protocol | No | Yes\. A channel can contain a maximum of three frame capture output groups\. | 
| HLS with a standard container or an fMP4 container | Send an HLS stream to a server that supports HTTP PUT or WebDav\. | HTTP server | Yes | Yes, when the output group is set up for VOD mode | 
| HLS with a standard container or an fMP4 container | Send an HLS stream to a server that supports HTTPS PUT or WebDav\. | HTTPS server | Yes | Yes, when the output group is set up for VOD mode | 
| HLS with a standard container or an fMP4 container | Send an HLS stream to an Akamai CDN\. | Akamai CDN, over HTTP or HTTPS | Yes | No | 
| HLS with a standard container only | Send an HLS stream to a MediaPackage channel using the HTTPS protocol\. | AWS Elemental MediaPackage, over HTTPS | Yes | No | 
| HLS with a standard container or an fMP4 container | Send an HLS stream to a container on MediaStore\. | AWS Elemental MediaStore, with a custom protocol | Yes | Yes, when the output group is set up for VOD mode | 
| HLS with a standard container or an fMP4 container | Send an HLS stream to an Amazon S3 bucket\. See [Amazon S3 Bucket Names](#s3-bucket-rule-anchor), after this table\. | Amazon S3, over a custom protocol | Yes | Yes, when the output group is set up for VOD mode | 
| MediaPackage | Send an HLS stream to a MediaPackage channel\. | AWS Elemental MediaPackage over an HTTPS WebDav | Yes | No | 
| Microsoft Smooth | Send a stream to an origin server or CDN that supports Microsoft Smooth Streaming\. | A supported CDN, over HTTP or HTTPS | Yes | No | 
| Multiplex | Create a transport stream \(TS\) that is part of a MediaLive multiplex\. |  | Yes | No | 
| RTMP | Send a stream to a server that supports the RTMP protocol\. | RTMP server | Yes | No | 
| RTMPS | Send a stream to a server that supports the RTMPS protocol\. | RTMPS server | Yes | No | 
| UDP | Send a transport stream \(TS\) to a server that supports UDP\. | UDP server | Yes | No | <a name="s3-bucket-rule-anchor"></a>

**Amazon S3 bucket names**

With MediaLive, the bucket name can't use *dot* notation\. For example, `mycompany-videos` is valid, but `mycompany.videos` isn't\. 