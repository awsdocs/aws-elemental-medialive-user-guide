# Supported Output Features<a name="processing-options"></a>

## Blanking and Blackout<a name="blanking-and-blackout-option"></a>

The “cue out” and “cue in” instructions in SCTE\-35 messages in TS inputs line up with specific content in the video, audio, and captions streams\. You can set up so that this content is blanked out in the output:
+ To blank out content for ad avails, use the ad avail blanking feature\. 
+ To blank out content for other messages, use the blackout feature\.

The behavior that you want must be set up in the channel\.

For more information, see [Enabling Ad Avail Blanking in the Output](enable-ad-avail-blanking.md) and [Enabling Blackout in the Output](enable-blackout.md)\.

## Manifest Decoration<a name="manifest-decoration-option"></a>

You can set up an output so that its manifest is decorated with ad avail information\. Manifest decoration works on two sources of ad avail information: 
+ Ad avail information found in the channel input, if the input is a transport stream \(TS\)
+ Ad avail information from SCTE\-35 messages added to the output using the MediaLive schedule

Manifest decoration applies only to HLS outputs, MediaPackage outputs, and Microsoft Smooth outputs:
+ You can set up HLS outputs so that their manifests are decorated according to one of the following styles:
  + Adobe
  + Elemental
  + SCTE\-35 enhanced
+ MediaPackage outputs are always set up so that their manifests are decorated\. The marker style is always SCTE\-35 enhanced style\. Keep in mind that if you don't actually want SCTE\-35 messages in the output that you deliver from AWS Elemental MediaPackage, then on the AWS Elemental MediaPackage side you can set up the channel to strip out the markers\. 
+ You can set up Microsoft Smooth outputs so that the sparse track includes instructions that correspond to the original SCTE\-35 message content\.

The behavior that you want must be set up in the channel\. For more information, see [Enabling Manifest Decoration in the Output](enable-manifest-decoration.md)\.

## SCTE\-35 Passthrough<a name="scte35-passthrough"></a>

You can set up TS outputs so that all the SCTE\-35 messages from the input are passed through to the output\. Or you can set up to remove these messages from the output\.

The behavior that you want must be set up in the channel\. For more information, see [Enabling SCTE\-35 Passthrough or Removal in the Output](scte-35-passthrough-or-removal.md)\.

## <a name="blanking-passthrough-manifest-decoration"></a>