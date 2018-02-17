# Creating a UDP Output Group<a name="creating-udp-output-group"></a>

Follow these steps if, when you were planning the channel, you determined that you want to include a UDP output group\.

1. On the **Create channel** navigation pane, go to the **Output groups** section and choose **Add**\. The content pane changes to show the **Add output group** section\. 

1. Choose **UDP** and choose **Confirm**\. More sections appear\. 

1. Complete the fields as described below\. 

1. When you have entered all the information for one output group, create another output group, if desired\. Otherwise, go to the next step\.

## UDP settings<a name="udp-settings"></a>

+ Enter a name for the output group\. For example, **Sports Game 10122017 ABR** or **tvchannel59**\.

+ Change the value of **Input loss action**, if desired\. 

+ Complete the **ID3** fields if applicable\.

## UDP destinations<a name="udp-destinations"></a>

Specify the URLs for two destinations\. You must specify two destinations because AWS Elemental MediaLive works in redundant mode for outputs: it requires two destinations\. The URLs must use the RTP or UDP protocol and must include a port number\. 

If FEC is enabled \(this field is in the Output panel, not the Output group panel\), then leave space between the port numbers for the two destinations\. For example, if one destination is **rtp://192\.0\.2\.0:5000**, then assume that FEC will also use port 5002 and 5004\. So the lowest possible port number for the other destination is 5005: **rtp://192\.0\.2\.230:5005**\.

## UDP outputs<a name="udp-outputs"></a>

This section contains fields related to the encoding of the video, audio, and captions in the output, and related to the packaging and delivery of the output\. 

Choose **Add output** if you want more than one output in this output group\. An **Output** line is added for each output\. Setup of the individual outputs is described in [[ERROR] BAD/MISSING LINK TEXT](creating-a-channel-step5.md)\.