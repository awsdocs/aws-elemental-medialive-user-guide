# Supported features by output type<a name="processing-applicability-by-output-type"></a>

This section describes which SCTE\-35 features apply to the various types of output\. 

**Topics**
+ [Archive output with MPEG\-2 container](archive-output-with-mpeg-2-container.md)
+ [Frame capture output](#framecapture-output)
+ [HLS output](hls-output.md)
+ [MediaPackage output](mediapackage-output.md)
+ [Microsoft Smooth output](ms-smooth-output.md)
+ [RTMP output](adobe-rtmp-output.md)
+ [UDP output](udp-ts-output.md)

## Frame capture output<a name="framecapture-output"></a>

In a frame capture output, MediaLive supports SCTE\-35 features as follows:
+ Passthrough of the SCTE\-35 messages – Not applicable\. 
+ Manifest decoration – Not supported because these outputs don't have manifests\.
+ Blanking and blackout – Applicable\. Content in the output is blanked or blacked out if the features are enabled at the channel level\.

A frame capture output doesn't support passthrough of the SCTE\-35 messages\. However, if blanking or blackout is enabled \(at the channel level\), then content that falls between the start and stop of the blackout is blanked or blacked out, even though no SCTE\-35 messages are present\. 