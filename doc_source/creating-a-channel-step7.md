# Step 8: Set Up the Audio Encodes<a name="creating-a-channel-step7"></a>

The output section for every type of output group \(Archive, Frame Capture, HLS, Microsoft Smooth, and UDP\) contains a **Stream settings** section\. In this section, you create [encodes](channels.md#encode) for the video, audio, and captions in the output and specify the details of how you want these assets encoded\. 

The following procedure describes how to set up an audio encode and assumes that you have [created the output ](creating-a-channel-step5.md) that will hold the audio\. The configuration options for an audio encode are identical for all output group types\. 

Note that a Frame Capture output group contains video but doesn't contain audio or captions\.

**To set up the audio encodes in the outputs**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output \(or the first output\) where you want to set up the audio encode\.

1. Choose the link for one of the audio encodes\. \(You might have created more than one encode\.\)

1. For **Codec settings**, choose the codec to use to encode this audio asset\. The remaining fields change to match this codec\.

1. Complete each field as appropriate\. For details about a field, choose the **Info** link next to the field\. 

1. Optionally complete the fields in the **Remix settings** section, or keep the defaults \(to omit remixing\)\.

1. Optionally complete the fields in the **Audio normalization** settings section, or keep the defaults \(to omit normalization\)\.

1. Repeat for each audio encode in this output, if any\.

1. Continue setting up the audio encodes, [video encodes](creating-a-channel-step6.md), and [captions encodes](creating-a-channel-step8.md) for all outputs in all output groups\. When you have finished with the encodes for all outputs, go to [save the channel](creating-a-channel-step9.md)\.