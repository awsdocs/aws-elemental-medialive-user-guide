# SCTE\-35 Message Processing<a name="scte-35-message-processing"></a>

SCTE\-35 messages are messages that accompany the video input in an MPEG\-2 transport stream \(TS\)\. These messages provide information about advertisement availability, also known as ad avail events, and other non\-ad avail events\. 

On the input side, SCTE\-35 messages can appear only in MPEG\-2 transport stream \(TS\) inputs, which means that in MediaLive they can appear only in RTP or HLS inputs\.

You can set up a channel so that if an input includes these messages, the messages are either processed during ingest \(passed through\) or ignored\.

MediaLive doesn't support processing of ad avail decorations in input manifests\. The ad avail decorations in input manifests are always ignored\.

On the output side, if you set up to pass through the input \(rather than ignore it\), then you can set up each output so that the SCTE\-35 messages from the input are turned into cueing information that is appropriate for that output type\. This cueing information can be in the form of one or both of the following:
+ SCTE\-35 messages in a TS output
+ Manifest \(or sparse track\) decoration

You set up each output separately, so that you can set up some outputs to include cueing information and some to exclude it\.

As an adjunct to the ad avail information, you can also set up the outputs to blank out the video, audio, and captions within the cueing information\.

**Note**  
To use the ad avail features of MediaLive, you should be familiar with the SCTE\-35 standard and optionally with the SCTE\-67 standard\. You should also be familiar with how the input that you are encoding implements those standards\.  
The information in this SCTE\-35 section assumes that you are familiar with the general steps for creating a channel, as described in [Creating a Channel from Scratch](creating-channel-scratch.md)\. It also assumes that you have started creating a channel, including associating an input with the channel\.

**Topics**
+ [About Message Processing](about-message-processing.md)
+ [Getting Ready: Set the Ad Avail Mode](getting-ready-set-the-ad-avail-mode.md)
+ [Enabling Manifest Decoration in the Output](enable-manifest-decoration.md)
+ [Enabling Ad Avail Blanking in the Output](enable-ad-avail-blanking.md)
+ [Enabling Blackout in the Output](enable-blackout.md)
+ [Enabling SCTE\-35 Passthrough or Removal in the Output](scte-35-passthrough-or-removal.md)
+ [Sample Manifests \- HLS](sample-manifests-hls.md)