# Identifying content in an HLS source<a name="extract-contents-hls"></a>

The content in an HLS container is always a transport stream \(TS\) that contains only one video rendition \(program\)\. 

Obtain identifying information from the content provider:
+ For video – Obtain the bitrates of the available video renditions\. 
+ For audio – Obtain the PIDs or three\-character language codes of the languages that you want\. 
**Note**  
We recommend that you obtain the PIDs for the audio assets\. They are a more reliable way of identifying an audio asset\. Use the language only if there is only one instance of each audio language in the audio asset\.
+ For captions – Obtain the languages in the channel numbers\. For example, "channel 1 is French"\. The captions are always embedded\-style, containing up to four languages, each with its own channel number\.