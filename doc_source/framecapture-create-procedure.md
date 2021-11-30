# Procedure to create a frame capture output group<a name="framecapture-create-procedure"></a>

Follow these steps to create a frame capture output group and output\.

**To create a Frame Capture output group and its output**

1. On the **Create channel** page, under **Output groups**, choose **Add**\. 

1. In the **Add output group** section, choose **Frame capture**, and then choose **Confirm**\. More sections appear\. 
   + **Destination** – This section contains fields for the [output destination](framecapture-destinations.md)\. 
   + **Frame capture settings** – This section contains a field for the output group name and for the [output destination](framecapture-destinations.md)\. 
   + **Frame capture outputs** – This section shows the output that is added by default\. A frame capture output can contain only one output, so don't click **Add output**\.

     To view the fields, choose the **Settings** link\. 

1. In **Frame capture outputs**, choose the **Settings** link to view the sections for the individual output:
   + **Output settings** – This section contains fields for the [output destination](framecapture-destinations.md)\.
   + **Stream settings** – This section contains fields for the [output streams](output-settings-framecapture.md) \(the video, audio, and captions\)\.

1. \(Optional\) Enter names for the output group and the output:
   + In **Frame capture settings**, for **Name**, enter a name for the output group\. This name is internal to MediaLive; it doesn't appear in the output\. For example, **Sports Game Thumbnails**\.
   + In **Frame capture outputs**, for **Name**, enter a name for the output\. This name is internal to MediaLive; it doesn't appear in the output\.

1. To complete the other fields, see the topics listed after this procedure\.

1. After you have finished setting up this output group and its single output, you can create another output group \(of any type\), if your plan requires it\. Otherwise, go to [Step 9: Save the channel](creating-a-channel-step9.md)\.