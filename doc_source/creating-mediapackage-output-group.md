# Creating a MediaPackage Output Group<a name="creating-mediapackage-output-group"></a>

Follow these steps if, when you were [planning the channel](planning-workflow.md), you determined that you want to include a MediaPackage output group\.

**To create a MediaPackage output group**

1. On the **Create channel** page, in the **Output groups** section, choose **Add**\. The content pane changes to show the **Add output** group section\. 

1. Choose **MediaPackage**, and then choose **Confirm**\. More sections appear\. 

1. For **MediaPackage channel ID**, enter the channel ID for that channel\. You made a note of this ID when you [set up the channel](downstream-system-emp.md) on AWS Elemental MediaPackage\.

   MediaLive automatically sets up the output group as follows:
   + The output is delivered to AWS Elemental MediaPackage using WebDAV\. The output is always a live stream, not a VOD stream\.
   + For a MediaPackage output group, if input into MediaLive is lost then the behavior is for MediaLive to pause delivery\. AWS Elemental MediaPackage expects this behavior and handles the loss by switching to the other input\.
   + The codec specification is RFC 4281\. The playout device might use this information\.
   + SCTE\-35 ad markers are always enabled\. If you don't want SCTE\-35 markers, you will be able to remove them in the AWS Elemental MediaPackage channel\. For information about SCTE\-35 handling in a MediaPackage output, see [SCTE\-35 Message Processing](scte-35-message-processing.md)\.
   + The ability to insert ID3 markers through the output group is disabled\. However, you can set up to pass through ID3 markers that are in the input, and you can insert ID3 markers using the MediaLive schedule\. For information about ID3 handling in a MediaPackage output, see [Working with ID3 Metadata](id3-metadata.md)\.
   + The output name or names are automatically set to `Output n`, where n is an integer starting at 1\. 
   + The name modifier for each output is automatically set to match the output name\.
   + The program date time \(PDT\) period is set to 1 second\.

1. When you are ready, go to the [next step](creating-a-channel-step5.md)\.