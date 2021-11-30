# The procedure for input handling<a name="color-space-input-procedure"></a>

**Note**  
If you plan to remove the color space metadata from *all* the outputs, there is no point to correcting the metadata, so you can leave the default configuration for the inputs\. Skip to [The procedure for output handling](colorspace-output-procedure.md)\.

**To decide how to handle the color space metadata**

1. Contact the content provider to determine what color space or color spaces apply to each video source\. One individual source might contain a combination of different color spaces, particularly if the content is a VOD asset that is a few years old\. 

   Obtain the names of the color spaces\.

   If the video source is from an AWS Elemental Link device and the color space is HDR10, also obtain the Max CLL and Max FALL values that apply to the content\. \(Only HDR10 has these two values\.\)

1. Find out from the content provider if the color space metadata is accurate\. The content might be any of the following:
   + Correctly marked\.
   + Incorrectly marked\. This case is more common with older SDR content\.
   + Unmarked \(no color space metadata is present\)\.
   + Correctly marked but unreadable\. This case always applies when the input is from an AWS Elemental Link device\.
   + Marked as *unknown*\.
   + Marked with a color space that MediaLive doesn't support\.

   One source content might be any combination of marked, unknown, and unmarked\.

1. Decide if you need to add or clean up the color space metadata in each input\. If you plan to include color space metadata in at least one output \(either passed through from the input, or converted\), then you should add it or clean it up, as appropriate\.
**Note**  
If you plan to remove color space metadata from all of the outputs, there is no need to clean it up\. You can pass it through to the output as is\. You can stop reading this procedure\.

   For information on your choices for different content, see the tables in [Clean up scenarios for color space metadata](color-space-cleanup-scenarios.md)\.

   The following rules apply:
   + The cleanup options don't *convert* the color space metadata\. They *mark it*—MediaLive inserts metadata that is missing, or it changes the metadata for incorrectly marked content\.
   + Only clean up the color space if you are sure that all the unmarked portions use the color space that you choose\. If the cleanup results in marking content as being in a specific color space when it isn't, then the video color quality will be degraded in the output\.
   + If you are planning to convert the color space on the output side, keep in mind that this conversion will apply only to marked content\. So if you use cleanup to insert missing metadata, you can increase the percentage of the content that gets converted in the output\. 

**To set up each input attached to the channel**
**Note**  
This section assumes that you are familiar with creating or editing a channel, as described in [Creating a channel from scratch](creating-channel-scratch.md)\. 

1. On the **Create Channel** page, in the **Input attachments** section, for **Video selector**, choose **Video selector**\. 

1. Set the appropriate values for **Color space** and **Color space usage**\. These two fields control correction to the color space metadata\. 

   In the following table, each row shows a valid combination of the two fields and the result of that combination\.     
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/color-space-input-procedure.html)

1. This step applies only if you chose **HDR10** and the attached input is for a MediaLive device\. You must specify the values for the Max CLL and Max FALL for the content\. You should have obtained this information from the content provider\.

   For **Color space settings**, choose **HDR10**\. In the two fields that appear, enter the values\.