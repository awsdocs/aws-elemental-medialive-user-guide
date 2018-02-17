# Planning the Channel<a name="planning-the-channel"></a>

1. For the specified input, identify the output protocols \(for streaming outputs\) or the number of different output file types \(for archive outputs\)\. 

   For example, you could create a streaming ABR HLS output asset, a streaming non\-ABR HLS output asset, and an archive version of the HLS output asset \(containing the highest bitrate video\)\. You could also create a streaming ABR Smooth output asset\. 

1. For the first output asset, identify the number of video encodes that you need\. 

   + Some output assets consist of one video encode \(one set of encoding settings\)\. In this case, you will plan to create an output group that contains one video output\.

   + An ABR output asset will have more than one video encode – for example, one high\-bitrate video, one medium\-bitrate video, and one low\-bitrate video\. The encoding instructions are identical \(for example, they all use H\.264\) except for the bitrate\. In this case, you will plan to create an output group with more than one video output\.

1. For the first output asset, identify the audio encodes you need\.

   Typically, you need one encode for each language \(English, French, etc\)\.

1. For the first output asset, identify the captions your need\.

   Typically, you need one encode for each captions language \(English, French, etc\)\.

1. Group these encodes into outputs, as described in [[ERROR] BAD/MISSING LINK TEXT](examples-channel-design.md)\. Make sure the groupings follow the rules for encodes in outputs\.

1. Group the outputs into one output group\. For example, group the outputs for the ABR HLS outputs into one output group\.

1. Repeat the design of encodes, outputs, and output group for each output asset\.