# Planning the Inputs<a name="planning-the-input"></a>

To plan your input or inputs, identify which individual video, audio, and captions assets you want to extract from each input and which ones that you want to omit\. For example, you must extract one video file, but you can choose to omit some captions languages\.

The rules for extracting input are the following: 
+ You must extract one and only one video file from each input\. 

  If the channel will have multiple inputs, there is no requirement for the video properties in the various inputs to be identical in terms of codec, resolution, frame rate, color space, scan type, and so on\. So, for example, the video in one input might be HEVC, while the video in another input might be H\.264\. 
+ You can extract zero or more audio files from each input\. Typically, you extract multiple audio files so that you can include multiple languages in the output\. But you can also extract multiple audio files to extract different audio formats, for example, AAC and Dolby Digital\. 

  If the channel will have multiple inputs, there is no requirement for the audio files in the various inputs to be identical in terms of codec, sample rate, bitrate, and so on\. 
+ You can extract zero or more captions files\. 

  If the channel will have multiple inputs, read the information about setting up for captions in [Captions in Channels with Multiple Inputs](captions-channels-multi-input.md)\.