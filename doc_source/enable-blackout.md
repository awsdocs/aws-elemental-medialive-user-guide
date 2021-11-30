# Enabling blackout in the output<a name="enable-blackout"></a>

You can enable blackout to blank out the content for an SCTE\-35 message that is of type “other event” \(as defined by the mode in [Getting ready: Set the ad avail mode](getting-ready-set-the-ad-avail-mode.md)\)\. For example, chapters and programs\.

\(A similar feature is described in [Enabling ad avail blanking in the output](enable-ad-avail-blanking.md)\.\)

Blackout involves the following processing:
+ Replace the video content associated with the event with an image that you specify or is with a black image\.
+ Remove the audio that is associated with the event\.
+ Remove the captions that are associated with the event\.

**Comparison to manifest decoration and passthrough**

Blackout applies to all outputs\. You cannot choose to black out for some outputs \(for example, the HLS output\) and not black out for others \(for example, the Microsoft Smooth output\)\. It is an all\-or\-nothing decision\. 

Manifest decoration and passthrough have a smaller scope: they apply only to outputs that support these features\. 

**Important**  
Take note of this fact, because if you do *not* do passthrough and do *not* do manifest decoration in a specific output \(because they are not supported or because you choose not to\) but you do implement blanking, there will be no “markers” for where the blanked content occurs\. The only way of identifying where this blanking is occurring will be to look for the IDR i\-frames that identify where the SCTE\-35 message used to be\.

**Topics**
+ [Enabling blackout](procedure-enable-blackout.md)
+ [Triggers for blackout](triggers-for-blackout.md)
+ [Blackout restriction flags](blackout-restriction-flags.md)