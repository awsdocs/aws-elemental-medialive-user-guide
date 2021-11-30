# Procedure to create an archive output group<a name="archive-create-procedure"></a>

Follow these steps to create an archive output group and output\.

**To create an archive output group and its output**

1. On the **Create channel** page, under **Output groups**, choose **Add**\. 

1. In the **Add output group** section, choose **Archive**, and then choose **Confirm**\. More sections appear:
   + **Archive group destination** – This section contains fields for the [output destination](archive-destinations.md)\. 
   + **Archive settings** – This section contains fields for the [output destination](archive-destinations.md)\. 
   + **Archive outputs** – This section shows the output that is added by default\. An archive output can contain only one output, so don't click **Add output**\.

1. In **Archive outputs**, choose the **Settings** link to view the sections for the individual output:
   + **Output settings** – This section contains fields for the [output destination](archive-destinations.md) and the [output container](archive-container.md)\.
   + **Stream settings** – This section contains fields for the [output streams](archive-streams.md) \(the video, audio, and captions\)\.

1. \(Optional\) Enter names for the output group and the output:
   + In **Archive settings**, for **Name**, enter a name for the output group\. This name is internal to MediaLive; it doesn't appear in the output\. For example, **Sports Game 10122017 ABR** or **tvchannel59**\.
   + In **Archive outputs**, for **Name**, enter a name for the output\. This name is internal to MediaLive; it doesn't appear in the output\.

1. To complete the other fields, see the topics listed after this procedure\.

1. After you have finished setting up this output group and its single output, you can create another output group \(of any type\), if your plan requires it\. Otherwise, go to [Step 9: Save the channel](creating-a-channel-step9.md)\.