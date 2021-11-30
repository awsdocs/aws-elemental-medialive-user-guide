# Ingesting ancillary data from SMPTE\-2038 in an MPEG\-2 TS<a name="smpte-2038"></a>

You can configure MediaLive to extract specific ancillary data from a SMPTE\-2038 PID contained in these inputs:
+ HLS transport stream \(TS\) inputs 
+ MediaConnect inputs
+ RTP inputs

MediaLive can extract the following data from a SMPTE\-2038 that is included in one of these inputs:
+ ARIB captions – Captions that are compliant with ARIB STD\-B37 version 2\.4\.
+ Embedded captions – Captions carried as ancillary captions that are compliant with SMPTE 334\. The ancillary captions themselves must be compliant with EIA\-608 standard \(also known as CEA\-608 or “line 21 captions”\) or CEA\-708 standard \(also known as EIA\-708\)\.
+ Teletext captions – OP47 teletext format, also known as SMPTE RDD\-08 \(compliant with ITU\-R BT\.1120\-7\)\.
+ Timecode – A SMPTE 12M timecode\. MediaLive recognizes this timecode as an embedded timecode source\.

**Note**  
This section assumes that you are familiar with creating or editing a channel, as described in [Creating a channel from scratch](creating-channel-scratch.md)\. 

**Well\-formed SMPTE\-2038 source**  
For MediaLive to extract and process the data appropriately, the SMPTE\-2038 must meet certain criteria:
+ The SMPTE\-2038 must be present in every PMT\.
+ The PID in which the SMPTE\-2038 is located must not change in the stream\. There is no support for changing the PID and sending a new PMT identifying that PID\.
+ The stream should contain the SMPTE\-2038 in only one PID\. If it's present in more than one PID, there's no guarantee that MediaLive will identify the PID that appears first\. It could choose another PID, with results you don't intend\.

**To configure the channel to use the SMPTE\-2038 data**  
You can specify how you want MediaLive to use SMPTE\-2038 data that is in the input\.

1. On the **Create channel** page, find the **Input attachment** for the relevant input\.

1. In **General input settings**, set **Prefer SMPTE\-2038** to one of the following:
   + **Prefer** – For a specific item of data, MediaLive first looks for the data in a SMPTE\-2038 PID\. If the data is not found in the SMPTE\-2038 or if there is no SMPTE\-2038, MediaLive looks for the data in other locations in the stream\.
   + **Ignore** \(default\) – MediaLive never looks for a SMPTE\-2038 PID\. Even if a specific item of data is not available in other places in the stream, MediaLive doesn't look for a SMPTE\-2038 PID\. For example, if you set the timecode source to *embedded* and there is no timecode source in the video stream, MediaLive won't look for it in a SMPTE\-2038\.

**How MediaLive uses the SMPTE\-2038 data**  
If you set up to prefer SMPTE\-2038 data, MediaLive handles the data as follows:
+ Captions – In the **Input attachment** section for the relevant input, you might set up a captions selector that specifies **ARIB**, **Embedded**, or **Telextext**\. MediaLive first looks for the specified type of captions in the SMPTE\-2038\. If MediaLive doesn't find the captions there, it looks in other locations in the stream\.

  Regardless of where MediaLive finds the captions, when MediaLive extracts them, it processes them in the usual way, according to how you set up for [captions in the output](create-captions-encodes.md)\.
+ Timecode – In the **General settings** section for channel, in the **Timecode configuration** section, you might set the **Source** to **Embedded**\. MediaLive first looks for a SMPTE 12M timecode in the SMPTE\-2038\. If MediaLive doesn't find the captions there, it looks for a timecode embedded directly in the video stream\. 

  MediaLive associates the SMPTE 12M timecode with the closest video frame\. For information on how MediaLive uses the timecode, see [How timecode works at runtime ](timecode-runtime.md)\.