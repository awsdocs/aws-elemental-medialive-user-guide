# Timecode configuration<a name="timecode"></a>

You can set up the channel to include timecode metadata in the individual output encodes for any type of output group except Frame Capture\. The timecode in the output is an SEI message of type `pic_timing`\.

You configure timecode in two places in the channel—the input and the output\.
+ On the input side, you specify the source for the timecode\. 
+ On the output side, in each video encode, you specify whether to include the timecode\. By default, the timecode is not included in the video encode\.

Time in the channel runs on a clock \(not on a timer\)\. The time in the output is in 24\-hour format `hh:mm:ss:ff` and rolls over at midnight\. For more information about the behavior of the timecode, see [How timecode works at runtime ](timecode-runtime.md)\.

This section assumes that you are familiar with creating or editing a channel, as described in [Creating a channel from scratch](creating-channel-scratch.md)\.

**To configure the timecode source**

1. On the **Create Channel** page, in the **General settings** section, choose **Timecode configuration** 

1. For **Source**, set the appropriate value: 
   + **EMBEDDED** – Use the timecode in the source video\. If MediaLive doesn't find an embedded timecode in the source, it falls back to system clock timecode \(SYSTEMCLOCK\)\. If an embedded timecode is detected after you have started the channel, MediaLive will switch from the fall back system clock to the newly detected embedded timecode\.
   + **SYSTEMCLOCK**– Use the UTC time\. 
   + **ZEROBASED** – The time of the first frame in the output will be 00:00:00:00\.

   For embedded timecode, MediaLive looks for the timecode as follows:
   + MPEG2 – A timecode inserted in each GOP header, in accordance with section 6\.2\.2\.6 of ISO/IEC 13818\-2\-2000 \(R2006\)
   + H\.264 \(AVC\) – A timecode inserted in an SEI message of type pic\_timing, in accordance with section D\.1\.2 of ISO/IEC 14496\-10\-2005
   + H\.265 \(HEVC\) – A timecode inserted in an SEI message of type timecode, in accordance with section D\.2\.26 of ITU\-T H\.265

1. \(Optional\) For **Sync threshold**, enter a threshold \(in frames\) for synchronizing the current output timecode to the current input timecode\. For information about this field, see [About the synchronization threshold](timecode-sync.md)\.

**To include timecodes in the output**

1. On the **Create Channel **page, in the **Output groups **section, create an output or choose an existing output\.

1. Display the **Stream settings **section, and then choose the **Video **section\.

1. For **Codec settings**, choose the codec for this video encode\. More fields appear\.

1. For **Timecode**, for **Timecode insertion**, choose an option:
   +  **DISABLED** – This encode won't include timecode metadata\.
   + **PIC\_TIMING\_SEI** – This encode will include timecode metadata as an SEI message of type `pic_timing`, in accordance with section D\.1\.2 of ISO/IEC 14496\-10\-2005\.

**Topics**
+ [About the synchronization threshold](timecode-sync.md)
+ [How timecode works at runtime](timecode-runtime.md)