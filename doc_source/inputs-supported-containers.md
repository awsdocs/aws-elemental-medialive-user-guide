# Supported Input Types and Upstream Systems<a name="inputs-supported-containers"></a>

The following table lists the input types and protocols that MediaLive supports\. After the table are descriptions of the push and pull terms\. 


| MediaLive Input Type | Use Case | Upstream System and Supported Protocol | Live Stream Supported? | VOD Asset Supported? | 
| --- | --- | --- | --- | --- | 
| HLS | Pull an HLS stream or asset from an external endpoint using the HTTP protocol, with or without a secure connection\. | HTTP server orHTTPS server | Yes | Yes | 
| HLS | Pull an HLS stream or file from an AWS Elemental MediaStore container, using a secure connection\. | AWS Elemental MediaStore with a custom protocol | Yes | Yes | 
| HLS | Pull an HLS stream or file from an Amazon S3 bucket, with or without a secure connection\. | Amazon S3 over a custom protocol | Yes\. However, Amazon S3 isn't recommended as a source for a live stream\. | Yes | 
| MediaConnect | Push a transport stream \(TS\) from a flow in AWS Elemental MediaConnect\.This input uses a MediaConnect flow ARN, not a URI\. | AWS Elemental MediaConnect over an internal connection | Yes | No | 
| MP4 | Pull an MP4 file from an HTTP server, with or without a secure connection\. | HTTP server or HTTPS server | No | Yes, with \.mp4 file extension only | 
| MP4 | Pull an MP4 file from an Amazon Simple Storage Service bucket, with or without a secure connection\. | Amazon S3 over a custom protocol | No | Yes, with \.mp4 file extension only | 
| RTP | Push a transport stream \(TS\) to a fixed endpoint on MediaLive, using the RTP protocol\. | RTP server over RTP Push | Yes | No | 
| RTP | Push a transport stream \(TS\) in your VPC to a fixed endpoint on MediaLive, using the RTP protocol\. | Amazon VPC over RTP within a private cloud | Yes | No | 
| RTMP Pull | Pull a stream from an external endpoint using the RTMP protocol\. | RTMP server over RTMP Pull | Yes | Yes | 
| RTMP Push | Push a stream to a fixed endpoint on MediaLive using the RTMP protocol\.  | RTMP server over RTMP Push | Yes | No | 
| RTMP Push | Push a stream in your VPC to a fixed endpoint on MediaLive, using the RTMP protocol\.  | Amazon VPC over RTMP within a private cloud | Yes | No | 

## Ingesting with Push<a name="push-inputs"></a>

A push input works as follows: the source attempts to deliver to an endpoint that is specified in the MediaLive input\. In the case of RTP protocols, the source is unaware of whether the content is being ingested by the MediaLive channel\. In the case of RTMP, there must be a handshake between the source and the MediaLive channel so that the source will have information about the status of the input\. 

When the channel \(that is connected to this input\) is started, MediaLive reacts to the source \(RTP\) or responds to the handshake message \(RTMP\) and ingests it\. When the channel is not running, MediaLive does not react; the source continues to publish to the endpoint \(RTP\) or goes into a paused state \(RTMP\), but MediaLive ignores those actions\. 

A push input works only with a streaming source\.

## Ingesting with Pull<a name="pull-inputs"></a>

A pull input works as follows: the source continually publishes to an endpoint that is outside of MediaLive\. When the channel \(that is connected to the input\) is running, MediaLive connects to the input and ingests the content\. 

When the channel is not running, MediaLive does not connect to the input\. \(There might be other applications that do connect\.\) 

A pull input works with a streaming input \(where the source is continually being published\) or a file input \(where the source is made available on the endpoint and then does not change\)\. 