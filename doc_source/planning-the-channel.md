# Planning the Channel<a name="planning-the-channel"></a>

 To plan your channel, follow these guidelines:

1. Identify the output protocols \(for streaming outputs\) or the number of different output file types \(for archive and frame capture outputs\)\. 

   For example, you could create a streaming ABR HLS output asset, a streaming non\-ABR HLS output asset, and an archive version of the HLS output asset \(containing the highest bitrate video\)\. You could also create a streaming ABR Smooth output asset\. 

1. For the first output asset, identify the number of video encodes that you need: 
   + Some output assets consist of one video encode \(one set of encoding settings\)\. In this case, you should plan to create an output group that contains one video output\.
   + An ABR output asset will have more than one video encode, for example, one high\-bitrate video, one medium\-bitrate video, and one low\-bitrate video\. The encoding instructions are identical \(for example, they all use H\.264\) except for the bitrate\. In this case, you should plan to create an output group with more than one video output\.

1. For the first output asset, identify the audio encodes that you need\.

   Typically, you need one encode for each language \(English, French, and so on\)\.

1. For the first output asset, identify the captions that you need\.

   Typically, you need one encode for each captions language \(English, French, and so on\)\.

1. Group these encodes into outputs, as described in [Examples of Channel Designs](examples-channel-design.md)\. Make sure that the groupings follow the [rules for encodes in outputs](rules-for-encodes-in-an-output.md)\.

1. Group the outputs into one output group\. For example, group the outputs for the ABR HLS outputs into one HLS output group\.

1. Repeat the design of encodes, outputs, and output group for each output asset\.

Here's the result of running a channel that follows this design:
+ Each output that you create in the channel becomes one media asset\.
+ If a media asset includes manifests, one master manifest is created for each output group and one "variant manifest" is created for each output\.