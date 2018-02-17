# Processing Features<a name="processing-options"></a>

## Blanking and Blackout<a name="blanking-and-blackout-option"></a>

The “cue out” and “cue in” instructions in SCTE\-35 messages line up with specific content in the video, audio, and captions streams\. You can set up so that this content is blanked out in the output:

+ The content for ad avails is blanked out using the ad avail blanking feature\. 

+ The content for other messages is blanked out using the blackout feature\.

The behavior you want must be set up in the channel\.

For more information, see [[ERROR] BAD/MISSING LINK TEXT](enable-ad-avail-blanking.md) and [[ERROR] BAD/MISSING LINK TEXT](enable-blackout.md)\.

## Manifest Decoration<a name="manifest-decoration-option"></a>

+ HLS outputs can be set up so that their manifests include instructions that correspond to the original SCTE\-35 message content\. Decorate the HLS manifest with one or more of the following types of ad markers:

  + Adobe

  + Elemental

  + SCTE\-35 enhanced

+ Microsoft Smooth outputs can be set up so that the sparse track includes instructions that correspond to the original SCTE\-35 message content\.

The desired behavior must be set up in the channel\. For more information, see [[ERROR] BAD/MISSING LINK TEXT](enable-manifest-decoration.md)\.

## SCTE\-35 Passthrough<a name="scte35-passthrough"></a>

You can include \(pass through\) all the SCTE\-35 messages in the output data stream in any TS output\. Or you can  remove them\.

Removing messages does not prevent you blanking or blacking out video content\. The two options do not depend on each other\.

The desired behavior must be set up in the channel\. For more information, see [[ERROR] BAD/MISSING LINK TEXT](scte-35-passthrough-or-removal.md)\.

## Blanking Compared to Passthrough and Manifest Decoration<a name="blanking-passthrough-manifest-decoration"></a>

It is important to understand that the logic for blanking ad content works on the video content associated with the ad avail event, while the logic for passthrough and manifest decoration works on the actual SCTE\-35 message\. The video content and the SCTE\-35 message are different entities\.

This means that you can blank ad avails and not pass through SCTE\-35 messages, or not blank ad avails and not pass through SCTE\-35 messages and decorate the manifest, or any combination\. The actions are independent\.

The only exception to this rule is for HLS outputs: manifest decoration and passthrough are either both enabled or both disabled\.