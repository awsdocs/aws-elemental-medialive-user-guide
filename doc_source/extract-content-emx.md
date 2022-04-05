# Identifying content in a MediaConnect source<a name="extract-content-emx"></a>

The content in an AWS Elemental MediaConnect source is always a transport stream \(TS\)\. The TS is made up of one program \(SPTS\) or multiple programs \(MPTS\)\. Each program contains a combination of video and audio\. It might also contain embedded\-style or object\-style captions\. 

Obtain identifying information from the content provider:
+ For video – Choose the one video program that you want, and obtain its PID or bitrate\. \(The source content might contain more than one video program\.\) 

  If two video programs are identical, look at the audios and captions in each program\. Those might be different, in which case you should choose the video program that contains the audio or captions formats you want\.
+ For audio – For the same program as the video, obtain the PIDs or three\-character language codes of the audio languages that you want\.
**Note**  
We recommend that you obtain the PIDs for the audio assets\. They are a more reliable way of identifying an audio asset\. Use the language only if there is only one instance of each audio language in the audio asset\.
+ For captions – For the same program as the video, obtain the identifiers:
  + If the captions are embedded, obtain the languages in the channel numbers\. For example, "channel 1 is French"\. 
  + If the captions are object\-style captions \(for example, DVB\-Sub\), obtain the PIDs of the captions languages that you want\. 