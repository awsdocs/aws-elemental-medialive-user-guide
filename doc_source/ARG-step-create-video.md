# Step 3: Create the Video Outputs<a name="ARG-step-create-video"></a>

If you want to include video in the HLS output group, then follow this procedure for each video encode\.

This procedure involves the following fields in the output section of the HLS output group the Channel page in the console:
+ **Output settings** – **HLS settings**
+ **Output settings** – **HLS settings** – **Audio rendition sets**

**To create the video outputs**

1.  In the **HLS output group**, in **HLS outputs**, choose **Add output**\. Choose **Settings** to display the **Outputs **page for that output\.

1. In the **Output** page, set up as follows:
   + In **Stream settings**, choose **Audio 1** and choose **Remove audio**\. The output now contains only a video encode\. In an output group that includes audio rendition groups, each video encode must each be in a video\-only output\.
   + Set up the rest of the stream settings as described in [Fields for the video, audio, and captions streams \(encodes\)](hls-streams-section.md)\.

1. Complete the **Output settings** section as follows:
   + For **HLS settings**, choose **Standard hls** or **Fmp4**, as appropriate\.
   + For **Audio rendition sets**, enter the name of the audio renditions groups to associate with this video output\. Don't worry that you haven't created this name yet\. To associate the video output with more than one group, enter a comma\-separated list\. For example:

     **AAC group, DD group**