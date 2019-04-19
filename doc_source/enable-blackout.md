# Enabling Blackout in the Output<a name="enable-blackout"></a>

You can enable blackout to blank out the content for an SCTE\-35 message that is of type “other event” \(as defined by the mode in [Getting Ready: Set the Ad Avail Mode](getting-ready-set-the-ad-avail-mode.md)\)\. For example, chapters and programs\.

\(A similar feature is described in [Enabling Ad Avail Blanking in the Output](enable-ad-avail-blanking.md)\.\)

Blackout involves the following processing:
+ Replace the video content associated with the event with an image that you specify or is with a black image\.
+ Remove the audio that is associated with the event\.
+ Remove the captions that are associated with the event\.

**Comparison to Manifest Decoration and Passthrough**

Blackout applies to all outputs\. You cannot choose to black out for some outputs \(for example, the HLS output\) and not black out for others \(for example, the Microsoft Smooth output\)\. It is an all\-or\-nothing decision\. 

Manifest decoration and passthrough have a smaller scope: they apply only to outputs that support these features\. 

Take important note of this fact, because if you do *not* do passthrough and do *not* do manifest decoration in a specific output \(because they are not supported or because you choose not to\) but you do implement blanking, there will be no “markers” for where the blanked content occurs\. The only way of identifying where this blanking is occurring will be to look for the IDR i\-frames that identify where the SCTE\-35 message used to be\.

**Topics**
+ [Enabling Blackout](procedure-enable-blackout.md)
+ [Triggers for Blackout](triggers-for-blackout.md)
+ [Blackout Restriction Flags](blackout-restriction-flags.md)