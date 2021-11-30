# Input specifications settings<a name="input-specification"></a>

The **Input Specifications** settings include three fields that characterize the video in the input that you intend to use with this channel\. The fields are the following: 
+ Input codec
+ Input resolution
+ Maximum input bitrate 

You should have obtained information about these video characteristics when you [assessed the upstream system](evaluate-upstream-system.md) for each input source\.

**To complete the settings**

1. In your list of planned inputs, look at all the inputs except for any Elemental Link inputs\. Find the following codec, resolution, and bitrate:
   + Find the most resource\-intensive codec among all the inputs\. The codecs, from least to most intensive, are MPEG2, then AVC, then HEVC\. Make a note of the codec\. The input it appears in isn't relevant\.
   + Find the highest resolution tier among all the inputs\. The tiers, from lowest to highest, are SD, HD, UHD\. Make a note of the tier\. The input it appears in isn't relevant\. 
   + Find the highest bitrate among all the inputs\. Make a note of the bitrate\. The input it appears in isn't relevant\.

1. For each field, choose an option that meets or exceeds the value you identified for that field\. 

   Follow these tips: 
   + If your channel contains only one input and it is from an AWS Elemental Link device, leave the input specification fields with their defaults\. 
   + If you aren't sure about the processing requirements of your inputs, choose a higher option\. For example, if you aren't sure of the bitrate and you are trying to choose between 10 Mbps and 20 Mbps, then choose 20 Mbps, to be on the safe side\. Or if you aren't sure if your inputs use AVC \(H\.264\) or HEVC \(H\.265\), then choose HEVC\. 

**How MediaLive uses this information**  
MediaLive uses these values for billing and resource allocation purposes\.
+ For billing, MediaLive uses these fields to calculate the charges that you will incur on the input side\. You pay for the option that you specify\. For example, if you specify HD but the inputs are all actually SD, you will still be charged for HD\. 
+ For resource allocation, MediaLive uses these fields to allocate processing resources when you run this channel\. If you don't choose the correct option, MediaLive might not allocate sufficient processing resources\. Insufficient processing resources might mean that your channel output starts to degrade when the channel is running\.

MediaLive doesn't use these values for determining what is actually in the video for decoding purposes\. At ingest time, it still inspects the video to detect the source codec, resolution, and bitrate\. 