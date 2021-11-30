# Procedure to create a Microsoft Smooth output group<a name="smooth-create-procedure"></a>

Follow these steps to create a Microsoft Smooth output group and its outputs\.

**To create a Microsoft Smooth output group and its outputs**

1. On the **Create channel** page, in the **Output groups** section, choose **Add**\. 

1. In the **Add output group** section, choose **Microsoft Smooth**, and then choose **Confirm**\. More sections appear:
   + **Microsoft Smooth group destination** – This section contains fields for the [destination of the outputs](smooth-destinations.md)\.
   + **Microsoft Smooth settings** – This section contains fields for the [container](smooth-container.md), the [connection to the downstream system](smooth-destinations.md), and [resiliency](smooth-resiliency.md)\. 
   + **Microsoft Smooth outputs** – This section shows the single output that is added by default\.
   + **Event configuration** – This section contains fields for the [destination of the outputs](smooth-destinations.md) and the[container](smooth-container.md)\.
   + **Timecode configuration** – This section contains fields for the [timecode](smooth-timecode.md) in the outputs\.
   + **Sparse track** – This section contains fields for the [container](smooth-container.md)\.

1.  If your plan includes more than one output in this output group, then in **Microsoft Smooth outputs**, choose **Add output** to add the appropriate number of outputs\. 

1. In **Microsoft Smooth outputs**, choose the first **Settings** link to view the sections for the first output:
   + **Output settings** – This section contains fields for the [output destination](smooth-destinations.md), and the [container](smooth-container.md)\.
   + **Stream settings** – This section contains fields for the [output streams](smooth-streams-section.md) \(the video, audio, and captions\)\.

1. \(Optional\) Enter names for the output group and the outputs:
   + In **Microsoft Smooth settings**, for **Name**, enter a name for the output group\. This name is internal to MediaLive; it doesn't appear in the output\. For example, **Sports Curling**\.
   + In the **Output settings** section for each output, for **Output name**, enter a name for the output\. This name is internal to MediaLive; it doesn't appear in the output\. For example, **high resolution**\.

1. To complete the other fields, see the topics listed after this procedure\.

1. After you have finished setting up this output group and its outputs, you can create another output group \(of any type\), if your plan requires it\. Otherwise, go to [Step 9: Save the channel](creating-a-channel-step9.md)\.