# Setting up an HLS source<a name="hls-upstream"></a>

This section describes how to set up the source content on the upstream system, and how to create an HLS input that connects the upstream system to MediaLive\. 

With an HLS input, MediaLive connects to the upstream system when the channel starts and *pulls* the sources\. The upstream system is typically a server that acts as a location for the source content\. This server is not the camera or encoder at the start of the workflow\. 

This diagram illustrates the final result of this setup\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\hls-pull-uss-input.png)

To perform this setup, you must work with an operator at the upstream system\.

**Topics**
+ [Obtain information](#setup-hls-obtain-info)
+ [Create an HLS input](#setup-input-hls)
+ [Ensure correct setup on the HLS upstream server](#setup-uss-hls)
+ [Result of this procedure](#setup-hls-result)

## Obtain information<a name="setup-hls-obtain-info"></a>

Obtain the following information from the operator at the upstream system:
+ The locations \(URLs\) on the upstream server where the M3U8 manifest files are stored\.

  There are two URLs for a standard\-class input, or one URL for a single\-class input\. For information about input classes and their uses, see [Channel class and input class](class-channel-input.md)\.

  See the tables later in this section for the URL format and for examples\. 

  Make a note of the full URLs\.
+ The user name and password \(credentials\) to access the upstream server, if the upstream system requires authenticated requests, and to access the license server, if the [HLS source is encrypted](uss-obtain-info.md)\. You might need credentials for the upstream system, or for the license server, or both\.

  If you need credentials for both, the credentials must be identical for both servers\. When you [discussed any encryption requirements](planning-hls-input-encrypted.md) with the upstream system, you should have made sure that the license server uses the same credentials as the upstream system\.

  Note that these user credentials relate to user authentication, not to the protocol\. User authentication is about whether the upstream system or license server will accept your request\. The protocol is about whether the request is sent over a secure connection\. 

You need this information to create the HLS input\. 

**Upstream server is an HTTP or HTTPS server**


|  |  | 
| --- |--- |
| Format of URL | http//:<web server>\[:port\]/<path>/<file>\.m3u8orhttps//:<web server>\[:port\]/<path>/<file>\.m3u8 | 
| Example | https://203\.0\.113\.13/sports/curling\.m3u8 and`https://198.51.100.54/sports/curling.m3u8` | 

**Upstream server is AWS Elemental MediaStore**


|  |  | 
| --- |--- |
| Format of URL | mediastoressl://<data endpoint for container>/<path>/<file>\.m3u8 | 
| Example |  Assume that the data endpoint for the container for one of the content sources is the following: **eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com**\.  Assume that the `M3U8` file is called `curling.m3u8`, and it is stored in the container, in the path `sports/canada`\.  The URL for one of the content sources would be: **mediastoressl://eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com/sports/canada/curling\.m3u8**\.   | 

**Upstream server is Amazon S3**


| Upstream server | Format of URL | 
| --- | --- | 
| Format of URL | s3ssl://<bucket>/<path>/<file>\.m3u8 | 
| Example |  `s3ssl://DOC-EXAMPLE-BUCKET/movies/main/mlaw.m3u8` and  `s3ssl://DOC-EXAMPLE-BUCKET1/movies/redundant/mlaw.m3u8`  | 

## Create an HLS input<a name="setup-input-hls"></a>

You must create an input to connect MediaLive to the content source on the upstream server\. To create an HLS input, see [Creating an HLS pull input](input-create-hls-pull.md)\.

## Ensure correct setup on the HLS upstream server<a name="setup-uss-hls"></a>

An operator at the upstream server must set up the source content on the upstream system\. Make sure that the operator sets up as follows:
+ They set up to deliver the correct number of sources:
  + If the MediaLive channel is a standard channel, the operator must set up two sources for the content\. They must make sure that the two sources are identical in terms of video resolution and bitrate\.
  + If the MediaLive channel is a single\-pipeline channel, the operator must set up one source for the content\. 
+ They set up to make the M3U8 manifest files available at the agreed URLs\. These are the URLs that you obtained [earlier in this section](#setup-hls-obtain-info), and that you configured into the HLS input\. They correspond to the URLs shown in [the diagram after this procedure](#setup-hls-result)\.

## Result of this procedure<a name="setup-hls-result"></a>

As a result of this setup, an HLS input exists that specifies one or two *source* URLs\. These sources are the URLs for the source content on the upstream server\. 

At runtime of the channel, MediaLive will connect to the two URLs \(for a standard channel\) or the single URL \(for a single\-pipeline channel\), and pull the HLS manifests into MediaLive\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\hls-pull-uss-input.png)