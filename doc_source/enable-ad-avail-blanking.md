# Enabling Ad Avail Blanking in the Output<a name="enable-ad-avail-blanking"></a>

You can enable ad avail blanking to blank out the content for an SCTE\-35 message that is considered an ad avail \(as defined by the ad avail mode in [Getting Ready: Set the Ad Avail Mode](getting-ready-set-the-ad-avail-mode.md)\)\.

A similar feature is [blackout](enable-blackout.md)\.

Blanking involves the following processing:
+ Replace the video content associated with this event with an image that you specify or is with a black image\. 
+ Remove the audio that is associated with this event\. 
+ Remove the captions that are associated with this event\. 

## <a name="blanking-comparison-to-manifest-decoration-and-passthrough"></a>

**Comparison to Manifest Decoration and Passthrough**  
Ad avail blanking applies to all outputs\. You cannot choose to blank out for some outputs \(for example, the HLS output\) and not blank out for others \(for example, the Microsoft Smooth output\)\. It is an all\-or\-nothing decision\. 

Manifest decoration and passthrough have a smaller scope: they apply only to outputs that support these features\. 

**Important**  
Take note of this fact, because if you do *not* do passthrough and do *not* do manifest decoration in a specific output \(because they are not supported or because you choose not to\) but you do implement blanking, there will be no markers for where the blanked content occurs\. The only way to identify where this blanking is occurring will be to look for the IDR i\-frames that identify where the SCTE\-35 message used to be\.

**Topics**