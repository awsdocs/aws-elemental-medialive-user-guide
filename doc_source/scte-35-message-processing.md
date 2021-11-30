# SCTE\-35 message processing<a name="scte-35-message-processing"></a>

You can configure an AWS Elemental MediaLive channel to handle SCTE\-35 messages and SCTE\-104 messages\. These messages provide information about ad avails \(advertisement availability events\), and other non\-ad avail events\.

SCTE\-35 messages are messages that can be included in a source MPEG\-2 transport stream \(TS\)\. SCTE\-104 messages are messages that can be included in source content from an AWS Elemental Link hardware device\. SCTE\-104 messages are automatically converted into SCTE\-35 messages as soon as MediaLive ingests the input\. 

**Note**  
To use the ad avail features of MediaLive, you should be familiar with the SCTE\-35 standard and optionally with the SCTE\-67 standard\. You should also be familiar with how the input that you are encoding implements those standards\.  
This section assumes that you are familiar with creating or editing a channel, as described in [Creating a channel from scratch](creating-channel-scratch.md)\.

**Support for SCTE\-35 on the input side**

On the input side, SCTE\-35 messages can only appear in inputs containing MPEG\-2 transport streams \(TS\), which means that in MediaLive they can appear only in the following types of inputs:
+ Elemental Link inputs
+ HLS inputs
+ MediaConnect inputs
+ RTP inputs
+ Transport Stream \(TS\) File inputs
+ AWS CDI inputs

You can set up a channel so that if an input includes these messages, the messages are either processed during ingest \(passed through\) or ignored\.

**Support for SCTE\-35 on the output side**

On the output side, if you set up to pass through the input \(rather than remove it\), then you can set up each output so that the SCTE\-35 messages from the input are turned into cueing information that is appropriate for that output type\. This cueing information can be in the form of one or both of the following:
+ SCTE\-35 messages in a TS output
+ Manifest \(or sparse track\) decoration

You set up each output separately, so that you can set up some outputs to include cueing information and some to exclude it\.

As an adjunct to the ad avail information, you can also set up the outputs to blank out the video, audio, and captions within the cueing information\.

**Topics**
+ [About message processing](about-message-processing.md)
+ [Getting ready: Set the SCTE\-35 source—segments or manifest](scte35-getting-ready-source.md)
+ [Getting ready: Set the ad avail mode](getting-ready-set-the-ad-avail-mode.md)
+ [Enabling manifest decoration in the output](enable-manifest-decoration.md)
+ [Enabling ad avail blanking in the output](enable-ad-avail-blanking.md)
+ [Enabling blackout in the output](enable-blackout.md)
+ [Enabling SCTE\-35 passthrough or removal](scte-35-passthrough-or-removal.md)
+ [Inserting SCTE\-35 messages using the schedule](setup-scte35-insertion.md)
+ [Sample manifests \- HLS](sample-manifests-hls.md)