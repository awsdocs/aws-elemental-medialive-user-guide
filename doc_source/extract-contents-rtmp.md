# Identifying content in an RTMP source<a name="extract-contents-rtmp"></a>

This procedure applies to both RTMP push and pull inputs from the internet, and to RTMP inputs from Amazon Virtual Private Cloud\. The content in an RTMP input always consists of one video and one audio\. It might also contain embedded\-style captions\. 

Obtain identifying information from the content provider:
+ For video – You don't need identifying information\. MediaLive always extracts the single video asset\.
+ For audio – You don't need identifying information\. MediaLive always extracts the single audio asset
+ For captions – Obtain the languages in the channel numbers\. For example, "channel 1 is French"\. The captions are always embedded\-style, containing up to four languages, each with its own channel number\. The captions might be embedded in the video track or might be embedded in an ancillary track\.