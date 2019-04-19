# Input Specifications Settings<a name="input-specification"></a>

The **Input Specifications** settings include three fields that characterize the video in the input that you intend to use with this channel\. The values in these fields are used to calculate the charges that you will incur on the input side\. The values also ensure that MediaLive allocates sufficient processing resources when you run this channel\. The fields are the following: 
+ Input codec
+ Input resolution
+ Maximum input bitrate 

All the fields provide options that cover ranges, with the lowest range shown first and the highest shown last\. Lower ranges imply lower processing requirements, and higher ranges imply higher requirements\. 

For each field, choose an option that meets or exceeds the requirements of your input\. If your plan is for your channel to have more than one input, choose the option that meets or exceeds the most demanding of your inputs\. 

If you don't choose the correct option, MediaLive might not allocate sufficient processing resources\. If you aren't sure about the processing requirements of your input, choose a higher option\. For example, if you aren't sure of the bitrate and you are trying to choose between 10 Mbps and 20 Mbps, then choose 20 Mbps, to be on the safe side\. Even with codecs, this advice applies\. For example, if you aren't sure if your input is AVC \(H\.264\) or HEVC \(H\.265\), then choose HEVC\. 

MediaLive uses these values for billing and resource allocation purposes: you pay for the option that you specify\. For example, if you specify HD but the input is actually SD, you will be charged for HD\. 

MediaLive doesn't use these values for determining what is actually in the video for decoding purposes\. At ingest time, it still inspects the video to detect the source codec, resolution, and bitrate\. 