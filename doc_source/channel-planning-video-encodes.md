# Identify the video encodes<a name="channel-planning-video-encodes"></a>

You must decide on the number of video encodes and their codecs\. Follow this procedure for each output group\. 

1. Determine the maximum number of encodes that are allowed in the output group\. The following rules apply for each type of output group\.  
****    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/channel-planning-video-encodes.html)

1. If the output group allows more than one video encode, decide how many you want\. Keep in mind that you can create multiple output encodes from the single video source that MediaLive ingests\.

1. Identify the codec or codecs for the video encodes\. 
   + For most types of output groups, the downstream system dictates the codec for each video encode, so you obtained this information when you [identified the output encodes](#channel-planning-video-encodes)\. 
   + For an archive output group, you decide which codec suits your purposes\.

1. Identify the resolution and bitrate for each video encode\. You might have obtained requirements or recommendations from your downstream system when you [identified the output encodes](#channel-planning-video-encodes)\. 