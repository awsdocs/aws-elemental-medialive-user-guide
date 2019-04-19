# Step 9: Set up the Captions Encodes<a name="creating-a-channel-step8"></a>

The output section for every type of output group \(Archive, HLS, MediaPackage, Frame Capture, Microsoft Smooth, and UDP\) contains a **Stream settings** section\. In this section, you create [encodes](channels.md#encode) for the video, audio, and captions in the output and specify the details of how you want these assets encoded\. 

Note that a Frame Capture output group contains video but doesn't contain audio or captions\.

Before setting up captions, see [Reference: Supported Captions](supported-captions.md)\. There are rules about the following:
+ What captions formats can be generated, depending on the format of the input captions and container\. For example, ARIB can be generated only from ARIB input captions, which can appear only in a TS input\.
+ What captions type \(embedded, object, sidecar\) applies to which captions format\. For example, DVB\-Sub is an object type of format\.
+ Which format can be included in which type of output asset\. For example, HLS can take WebVTT \(a sidecar type\), 608 \(embedded\), and burn\-in\.

**To set up the captions encodes in the outputs**

1. For detailed information about setting up captions, see [Working with Captions](captions.md)\.

1. After you set up the captions for one output, continue setting up the [audio encodes](creating-a-channel-step7.md), [video encodes](creating-a-channel-step6.md), and captions encodes for all outputs in all output groups\. When you have finished with the encodes for all outputs, go to [save the channel](creating-a-channel-step9.md)\.