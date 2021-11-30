# Inputs<a name="audio-only-inputs"></a>

## Setting up the input source<a name="audio-only-input-source"></a>

The channel can have a single input or multiples inputs\. All the output groups—both those that are audio\-only and those that are video\-and\-audio—always ingest the same inputs\.

You can use one of the following two categories of input\.
+ Input that contains *only audio*\. In this case, the input must be one of these inputs:
  + MediaConnect input
  + RTP input
+ Input that contains *both audio and video* \(and optionally captions\)\. In this case, the input can be any input type that MediaLive supports\.

## Setting up input attachments<a name="audio-only-input-attachment"></a>

In each input attachment, create as many audio selectors as you require\. For example, create a selector for each language to extract\. Or create a selector for each audio quality or codec that is available\. 

Keep in mind that in a channel with both audio\-only and audio\-and\-video output groups, you don't have to create special audio selectors for the sole use of the audio\-only output\. The same audio selector can be used by both audio\-only and audio\-and\-video output groups\.