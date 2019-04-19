# Creating a UDP Output Group<a name="creating-udp-output-group"></a>

Follow these steps if, when you were [planning the channel](planning-workflow.md), you determined that you want to include a UDP output group\.

**To create a UDP output group**

1. On the **Create channel** page, in the **Output groups** section, choose **Add**\. The **Add output group** section appears\. 

1. Choose **UDP**, and then choose **Confirm**\. More sections appear\. 

1. Complete the fields in [each section](#udp-settings)\. 

1. After you enter all the information for one output group, you can optionally create another output group\. Otherwise, go to the [next step](creating-a-channel-step5.md)\.

## UDP Settings<a name="udp-settings"></a>
+ Enter a name for the output group\. For example, **Sports Game 10122017 ABR** or **tvchannel59**\.
+ Optionally change the value of **Input loss action**\. 
+ Optionally complete the **ID3** fields\. You use these fields to insert timed ID3 metadata into all the outputs in this output group\. For detailed information, see [Inserting ID3 Metadata When Creating the Channel](insert-timed-metadata.md)\.

## UDP Destinations<a name="udp-destinations"></a>

For the URLs for the destinations \(A and B\), specify two destinations when the channel is set up as a [standard channel](channel-class.md), or one destination when it is set up as a single\-pipeline channel\. The URLs must use the RTP or UDP protocol and must include a port number\. 

If FEC is enabled \(this field is in the **Output** pane, not the **Output group** pane\), then leave space between the port numbers for the two destinations\. For example, if one destination is **rtp://203\.0\.113\.28:5000**, assume that FEC also uses port 5002 and 5004\. So the lowest possible port number for the other destination is 5005: **rtp://203\.0\.113\.33:5005**\.

## UDP Outputs<a name="udp-outputs"></a>

This section contains fields that relate to the encoding of the video, audio, and captions in the output, and that relate to the packaging and delivery of the output\. 

If you want more than one output in this output group, choose **Add output**\. An **Output** line is added for each output\. Setup of the individual outputs is described in [Step 6: Create Outputs](creating-a-channel-step5.md)\.