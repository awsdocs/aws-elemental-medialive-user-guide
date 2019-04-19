# MP4 Pull<a name="planning-mp4-pull"></a>
+ MediaLive works with redundant sources, so you provide two video streams\. For optimized redundancy, MediaLive runs each source on different encoder pipelines in different Availability Zones\. You don't have to set up these Availability Zones because MediaLive does it for you\. 
+ Make sure that the two files are identical in terms of resolution and bitrate\. 
+ Keep in mind that the video source must be ready to be pulled before the channel starts to ingest the input\. 
  + If this input is the only input or the first input in the channel, it must be ready before you start the channel\. 
  + If this input is not the first input, it must be ready approximately 30 seconds before the channel switches to this input\. 