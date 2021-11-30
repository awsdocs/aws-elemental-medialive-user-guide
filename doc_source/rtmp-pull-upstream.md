# Setting up an RTMP pull source<a name="rtmp-pull-upstream"></a>

This section describes how to set up the source content on the upstream system, and how to create an RTMP Pull input that connects the upstream system to MediaLive\. With an RTMP Pull input, MediaLive connects to the upstream system when the channel starts and *pulls* the sources\. 

With an RTMP pull input, the upstream system is typically an upstream server that serves as a location for the source content\. The server is not the camera or encoder at the start of the workflow\.

This diagram illustrates the final result of this setup\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\rtmp-pull-uss-input.png)

To perform this setup, you must work with an operator at the upstream system\.

**Topics**
+ [Obtain information](#setup-rtmp-pull-obtain-info)
+ [Create an RTMP pull input](#setup-input-rtmp-pull)
+ [Ensure correct setup on the RTMP upstream system](#setup-uss-rtmp-pull)
+ [Result of this procedure](#setup-rtmp-pull-result)

## Obtain information<a name="setup-rtmp-pull-obtain-info"></a>

Obtain the following information from your contact person at the upstream system:
+ The application name and application instance for the source content\. \(The application instance is also known as the *stream* or *stream key*\.\) There are two sources for a standard\-class input , or one source for a single\-class input\. For information about input classes and their uses, see [Channel class and input class](class-channel-input.md)\. For information about input classes and their uses, see [Channel class and input class](class-channel-input.md)\. 

  The operator of the upstream system might already have rules for assigning these names\. If not, you might have names that you would like to use\. Make sure that you and the operator of the upstream system are clear about these names\.

  In this example, the application name and instance name are identical\. But they could be different:

  Application name: `live`, and instance name `curling`

  Application name: `live`, and instance name `curling`
+ The public IP addresses that MediaLive will pull the source content from\.

  These addresses must include port 1935\. For example:

  `rtmp://203.0.113.13:1935`

  `rtmp://198.51.100.54:1935`
+ The user name and password to access the upstream system, if the upstream system requires authenticated requests\. Note that these user credentials relate to user authentication, not to the protocol\. User authentication is about whether the upstream system will accept your request\. The protocol is about whether the request is sent over a secure connection\.

You need this information to create the RTMP input\. 

## Create an RTMP pull input<a name="setup-input-rtmp-pull"></a>

You must create an input to connect AWS Elemental MediaLive to the content source on the upstream server\. To create an RTMP Pull input, see [Creating an RTMP pull input](input-create-rtmp-pull.md)\.

## Ensure correct setup on the RTMP upstream system<a name="setup-uss-rtmp-pull"></a>

An operator at the upstream server must set up the source content on the upstream system\. Make sure that the operator sets up as follows:
+ They set up to deliver the correct number of sources:
  + If the MediaLive channel is a standard channel, set up two sources for the content\. Make sure that the two source contents are identical in terms of video resolution and bitrate\.
  + If the MediaLive channel is a single\-pipeline channel, set up one source for the content\. 
+ They set up to make the content available at the agreed URLs, and they use the agreed application names and instance names\. These URLs are the URLs that you obtained [earlier in this section](mp4-upstream.md#setup-mp4-obtain-info), and that you configured into the RTMP input\. They correspond to the URLs shown in [the diagram after this procedure](rtmp-push-upstream.md#setup-result-rtmp-push)\. 

## Result of this procedure<a name="setup-rtmp-pull-result"></a>

As a result of this setup, an RTMP pull input exists that specifies one or two *source* URLs\. These sources are the URLs for the source content on the upstream system\. 

At runtime of the channel, the input will connect to two URLs \(for a standard channel\) or one URL \(for a single\-pipeline channel\), and pull the source content identified by the application name and instance name into MediaLive\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\rtmp-pull-uss-input.png)