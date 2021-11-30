# Setting up an MP4 source<a name="mp4-upstream"></a>

This section describes how to set up the source content on the upstream system, and how to create an MP4 input that connects the content source to AWS Elemental MediaLive\. With an MP4 input, MediaLive connects to the upstream system when the channel starts and *pulls* the sources\. 

This diagram illustrates the final result of this setup\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/mp4-pull-uss-input.png)

To perform this setup, you must work with an operator at the upstream system\.

**Topics**
+ [Obtain information](#setup-mp4-obtain-info)
+ [Create an MP4 input](#setup-input-mp4)
+ [Ensure correct setup on the MP4 upstream system](#setup-uss-mp4)
+ [Result of this procedure](#setup-result-mp4)

## Obtain information<a name="setup-mp4-obtain-info"></a>

Obtain the following information from the operator at the upstream system:
+ The URLs on the upstream system for the source file or files\. 

  There are two URLs for a standard\-class input, or one URL for a single\-class input\. For information about input classes and their uses, see [Channel class and input class](class-channel-input.md)\.

  See the table later in this section for the URL format and for examples\.

  Make a note of the full URLs\.
+ The user name and password to access the upstream system, if the upstream system requires authenticated requests\. Note that these user credentials relate to user authentication, not to the protocol\. User authentication is about whether the upstream system will accept your request\. The protocol is about whether the request is sent over a secure connection\.

You need this information to create the MP4 input\. 

The following tables show the format of the URLs on the different types of upstream systems that MediaLive supports for MP4 input\. 

**Upstream server is an HTTP or HTTPS server**


|  |  | 
| --- |--- |
| Format of URL | <protocol>//:<hostname>/<filename>\.mp4 | 
| Example | https://203\.0\.113\.13/filler\-videos/oceanwaves\.mp4`https://198.51.100.54/filler-videos/oceanwaves.mp4` | 

**Upstream server is AWS Elemental MediaStore**


|  |  | 
| --- |--- |
| Format of URL | mediastoressl://<data endpoint for container>/<path>/<filename>\.mp4 | 
| Example |  Assume that the data endpoint for the container for one of the content sources is the following: **f31z\.data\.mediastore\.us\-west\-2\.amazonaws\.com**\.  Assume that the file is called `oceanwaves.mp4`, and it is stored in the container, in the path `filler-video`\.  The URL for one of the source files would be: **mediastoressl://f31z\.data\.mediastore\.us\-west\-2\.amazonaws\.com/filler\-video/oceanwaves\.mp4**   | 

**Upstream server is Amazon S3**


| Upstream server | Format of URL | 
| --- | --- | 
| Format of URL | s3ssl://<bucket>/<path>/<filename>\.mp4 | 
| Example |  `s3ssl://DOC-EXAMPLE-BUCKET/filler-videos/main/oceanwaves.mp4`  `s3ssl://DOC-EXAMPLE-BUCKET/filler-videos/redundant/oceanwaves.mp4` With MediaLive, the S3 bucket name must not use dot notation\. For example, `EXAMPLE-BUCKET` is acceptable but `EXAMPLE.BUCKET` isn't\.   | 

## Create an MP4 input<a name="setup-input-mp4"></a>

You must create an input to connect AWS Elemental MediaLive to the content source on the upstream server\. To create an MP4 input, see [Creating an MP4 pull input](mp4-pull-input.md)\.

## Ensure correct setup on the MP4 upstream system<a name="setup-uss-mp4"></a>

An operator at the upstream server must set up the source content on the upstream system\. Make sure that the operator sets up as follows:
+ They set up to deliver the correct number of sources:
  + If the MediaLive channel is a standard channel, the operator must set up two file sources\. They must make sure that the two files are identical in terms of video resolution and bitrate\.
  + If the MediaLive channel is a single\-pipeline channel, the operator must set up one file source\. 
+ They set up to make the content available at the agreed URLs\. These URLs are the URLs that you obtained [earlier in this section](#setup-mp4-obtain-info), and that you configured into the MP4 input\. They correspond to the URLs shown in [the diagram after this procedure](#setup-result-mp4)\.

## Result of this procedure<a name="setup-result-mp4"></a>

As a result of this setup, a MediaLive input exists that specifies one or two *source* URLs\. These sources are the URLs for the source content on the upstream server\. 

At runtime of the channel, MediaLive will connect to those two URLs \(for a standard channel\) or one URL \(for a single\-pipeline channel\), and pull the source content into MediaLive\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/mp4-pull-uss-input.png)