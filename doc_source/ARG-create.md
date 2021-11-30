# Creating an output with an audio rendition group<a name="ARG-create"></a>

This section describes how to create audio rendition groups in an HLS output group and how to associate those groups with the appropriate video outputs \(if any\)\. The encodes and associations that you create are the following:
+ If you want to include video in the output group, then for each video asset, you create one video output containing one video encode\. The output can also contain embedded captions, but it can't include sidecar captions\. The output can't contain audio encodes\.
+ For each audio asset, you create one *audio\-only* output containing one audio encode and no other encodes\. 
+ You decide on an ID for each rendition group\. The ID is a name that you decide on\. For example *AAC audio group*\.
+ To group several audio outputs into one rendition group, you assign the same *audio group ID * to each audio output\. 
+ Finally, to associate the video output \(if any\) with the audio rendition group, you assign the *audio group ID *to that video output\. 

**Topics**
+ [Step 1: Identify the video and audio encodes](ARG-step-create-mapping.md)
+ [Step 2: Determine Defaults and Selection Rules](ARG-step-defaults.md)
+ [Step 3: Create the Video Outputs](ARG-step-create-video.md)
+ [Step 4: Create the audio outputs](ARG-step-create-audio.md)
+ [Summary](ARG-create-summary.md)