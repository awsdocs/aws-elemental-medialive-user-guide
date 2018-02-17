# Step 8: Set up the Captions Encodes<a name="creating-a-channel-step8"></a>

The output section for every type of output group \(Archive, HLS, Microsoft Smooth, and UDP\) contains a Stream settings section\. In the Stream settings section, you create "encodes" for the video, audio, and captions in the output and specify the details of how you want these assets encoded\. 

Before setting up captions, see [[ERROR] BAD/MISSING LINK TEXT](supported-captions.md)\. There are rules about:

1. What caption formats can be generated, depending on the format of the input captions and container\. For example, ARIB can only be generated from ARIB input captions, which can only appear in a TS input\.

1. What caption type \(embedded, object, sidecar\) apply to which caption format\. For example, DVB\-Sub is an object type of format\.

1. Which format can be included in which type of output asset\. For example, HLS can take Web\-VTT \(a sidecar type\), 608 \(embedded\) and burn\-in\.

For detailed information on setting up captions, see [[ERROR] BAD/MISSING LINK TEXT](captions.md)\.

Continue setting up the audio encodes, video encodes, and captions encodes for all outputs in all output groups\. When done, go to save the channel\.