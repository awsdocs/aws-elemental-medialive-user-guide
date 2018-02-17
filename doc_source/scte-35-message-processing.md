# SCTE\-35 Message Processing<a name="scte-35-message-processing"></a>

SCTE\-35 messages are messages that are embedded in the video input\. These messages provide information about advertisement availability, also known as ad avail events, and other non\-ad avail events\. 

You can include \(pass through\) or remove the cueing information that is conveyed by these messages in the output streams \(video, audio, closed captioning, data\) and any associated manifests\. AWS Elemental MediaLive does not support processing of manifests that are present in the input\. The information in input manifests is not ingested by AWS Elemental MediaLive or included in the output or the output manifest\.

You can also blank out the video, audio, and captions within the cueing information\.

To use the ad avail features of AWS Elemental MediaLive, you should be familiar with the SCTE\-35 standard and optionally with the SCTE\-67 standard\. You should also be familiar with how the input that you are encoding implements those standards\.

**Note**  
The information in this SCTE\-35 section assumes that you are familiar with the general steps for creating a channel, as described in [[ERROR] BAD/MISSING LINK TEXT](creating-channel-scratch.md)\. It also assumes that you have started creating a channel, including associating an input with the channel\.


+ [About Message Processing](about-message-processing.md)
+ [Getting Ready: Set the Ad Avail Mode](getting-ready-set-the-ad-avail-mode.md)
+ [Enabling Manifest Decoration](enable-manifest-decoration.md)
+ [Enabling Ad Avail Blanking](enable-ad-avail-blanking.md)
+ [Enabling Blackout](enable-blackout.md)
+ [SCTE\-35 Passthrough or Removal](scte-35-passthrough-or-removal.md)
+ [Sample Manifests \- HLS](sample-manifests-hls.md)