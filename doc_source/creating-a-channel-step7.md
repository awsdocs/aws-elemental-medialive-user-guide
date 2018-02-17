# Step 7: Set up the Audio Encodes<a name="creating-a-channel-step7"></a>

The output section for every type of output group \(Archive, HLS, Microsoft Smooth, and UDP\) contains a Stream settings section\. In the Stream settings section, you create "encodes" for the video, audio, and captions in the output and specify the details of how you want these assets encoded\. 

This section describes how to set up an audio encode and assumes you have created the output that will hold the audio\. Note that the configuration options for an audio encode are identical for all output group types\. 

1. In the Create channel navigation panel, find the output group \(which you have already created\)\. 

1. Under that output group, find the output \(which you have already created \) where you want to set up the audio encode\.

1. Choose the link for one of the audio encodes \(you may have created more than one encode\)\. 

1. In the Codec settings field, choose the codec to use to encode this audio asset\. The remaining fields change to match this codec\.

1. Complete each field as appropriate\. For details on a field, choose the Info link next to the field\. 

1. Complete the fields in the Remix settings section if desired, or leave the defaults \(to omit remixing\)\.

1. Complete the fields in the Audio normalization settings section if desired, or leave the defaults \(to omit normalization\)\.

1. Repeat for each audio encode in this output, if any\.

1. Continue setting up the audio encodes, video encodes, and captions encodes for all outputs in all output groups\. When done, go to save the channel\.