# Identifying content in an MP4 source<a name="extract-contents-mp4"></a>

The content in an MP4 source always consists of one video track, and one or more audio tracks\. It might also contain embedded\-style captions\. 

Obtain identifying information from the content provider:
+ For audio – Obtain the track numbers or three\-character language codes of the languages that you want\. 
**Note**  
We recommend that you obtain the tracks for the audio assets\. They are a more reliable way of identifying an audio asset\. Use the language only if there is only one instance of each audio language in the audio asset\.
+ For captions – Obtain the languages in the channel numbers\. For example, "channel 1 is French"\. The captions are always embedded\-style, containing up to four languages, each with its own channel number\. The captions might be embedded in the video track or might be embedded in an ancillary track\.