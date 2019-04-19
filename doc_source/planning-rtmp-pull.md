# RTMP Pull<a name="planning-rtmp-pull"></a>
+ MediaLive works with redundant sources, so you provide two video streams\. For optimized redundancy, MediaLive runs each source on different encoder pipelines in different Availability Zones\. You don't have to set up these Availability Zones because MediaLive does it for you\.
+ Make sure that the two streams are identical in terms of resolution and bitrate\. 
+ For a pull input, keep in mind that the video source must be ready to be pulled before you start the channel\. This rule applies for both HLS VOD inputs and HLS live inputs\.