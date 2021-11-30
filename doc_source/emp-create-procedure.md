# Procedure to create a MediaPackage output group<a name="emp-create-procedure"></a>

Follow these steps to create a MediaPackage output group and its outputs\.

**To create a MediaPackage output group and its outputs**

1. On the **Create channel** page, in the **Output groups** section, choose **Add**\. The content pane changes to show the **Add output** group section\. 

1. Choose **MediaPackage**, and then choose **Confirm**\. More sections appear: 
   + **MediaPackage destination**
   + **MediaPackage settings**
   + **MediaPackage outputs**–This section shows the single output that is added by default\.

1. In the **MediaPackage destination** section, for **MediaPackage channel ID**, enter the channel ID for that channel\. For example, `curlinglive`\.

1.  As part of the planning for this output group, you [discussed your requirements](origin-server-s3.md) with the MediaPackage user\. You should have obtained the following information:
   + The ID of the MediaPackage channel\. For example, `curlinglive`\.

1. \(Optional\) In the **MediaPackage settings** section, for **Name**, enter a name for the output group\.

1. If your plan includes more than one output in this output group, then in **MediaPackage outputs**, choose **Add output** to add the appropriate number of outputs\.

   You might want to add an output in order to implement trick\-play\. For more information about this feature and for instructions on setting it up in the channel, see [Trick\-play track via the Image Media Playlist specification](trick-play-roku.md)\.

1. Choose the first **Settings** link to view the sections for the first output\. The section contains fields for the [output streams](hls-streams-section.md) \(the video, audio, and captions\)\.

1. After you have finished setting up this output group and its outputs, you can create another output group \(of any type\), if your plan requires it\. Otherwise, go to [Step 9: Save the channel](creating-a-channel-step9.md)\.