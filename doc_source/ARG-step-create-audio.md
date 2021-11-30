# Step 4: Create the audio outputs<a name="ARG-step-create-audio"></a>

Follow this procedure for each audio encode in the HLS output group\.

This procedure involves the following fields in the output section of the HLS output group the Channel page in the console:
+ **Output settings** – **HLS settings**
+ **Output settings** – **HLS settings** –** Audio track type**
+ **Output settings** – **HLS settings** – **Audio group ID**
+ **Output settings** – **HLS settings** – **Segment type**

**To create each audio output**

1.  In the **HLS output group**, in **HLS outputs**, choose **Add output**\. Choose **Settings** to display the **Outputs **page for that output\.

1. In the **Output** page, set up as follows:
   + In **Stream settings**, choose **Video 1** and choose **Remove video**\. The output now contains only an audio encode\. In an output group that includes audio rendition groups, each audio encode must each be in its own output\.
   + Set up the rest of the stream settings in the usual way\.

1. Complete the **Output settings** section as follows:
   + For **HLS settings**, choose **Audio only hls**\. More fields appear\.
   + For **Audio track type**, choose the value you decided on for this audio encode when you [determined the default](ARG-step-defaults.md)\.
   + For **Audio group ID**, enter the name of the rendition group that you want this audio encode to belong to\. For example, enter **AAC group**\. One audio encode can belong to only one rendition group\. 
   + For **Segment type**, choose **AAC**\.

   Ignore **Audio only image**\. This field does not apply to audio rendition groups\.