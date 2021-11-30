# Step 6: Set up the video encode<a name="creating-a-channel-step6"></a>

In [Step 5: Create output groups and outputs](creating-a-channel-step4.md), you created the output groups and outputs that you identified when you planned the channel\. Each output section contains a **Stream settings** section\. You must now create all the video [encodes](channels.md#encode)\. 

**General procedure**  
Follow this general procedure to set up the video encode\.

1. Decide how you're going to create each encode:
   + From scratch\.
   + By sharing an encode that already exists in this output or another output in the channel\.
   + By cloning an encode that already exists in this output or another output in the channel\.

   You might have already made this decision\. If not, you should decide now\. For more information, see [Step 4: Design the encodes](designing-encodes.md)\.

   You can share or clone video encodes from one output to another in the same output group, or from one output to an output in another output group\.

1. Read the appropriate sections that follow\.

**Topics**
+ [Creating a video encode from scratch](#create-video-scratch)
+ [Creating a video encode by sharing](#create-video-share)
+ [Creating a video encode by cloning](#create-video-clone)

## Creating a video encode from scratch<a name="create-video-scratch"></a>

**To set up the video encodes in most types of output**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output where you want to set up a video encode\.

1. Choose the link for the video encode\.

1. For **Codec settings**, choose the codec to use for this encode\. More fields appear\.

1. Complete each field as appropriate\. For details about a field, choose the **Info** link next to the field\. 
   + For information about the **Width** and **Height** fields \(which define the video resolution\), choose the **Info** link for each field\. The frame rate affects the output charges for this channel\. For more information about charges, see [the MediaLive price list](https://aws.amazon.com/medialive/pricing/)\.
   + For information about the **Framerate** fields, choose the **Info** link for each field\. The frame rate affects the output charges for this channel\. For more information about charges, see [the MediaLive price list](https://aws.amazon.com/medialive/pricing/)\.
   + For information about the **Color space** fields, see [Color space handling in AWS Elemental MediaLive](color-space.md)\.
   + For information about the **Additional encoding setting**s fields, see [Setting up enhanced VQ mode](video-enhancedvq.md)
   + For information about the **Rate control** fields, see [Setting the rate control mode](video-encode-ratecontrol.md)\. There are fields in this section that affect the output charges for this channel\. For more information about charges, see [the MediaLive price list](https://aws.amazon.com/medialive/pricing/)\.
   + For information about the **Timecode** fields, see [Timecode configuration](timecode.md)\.
**Note**  
The **Width** and **Height** fields \(which define the video resolution\), the fields in the **Framerate** section, and the **Bitrate** field in the **Rate control** section all affect the output charges for this channel\. For more information about charges, see [the MediaLive price list](https://aws.amazon.com/medialive/pricing/)\.

**To set up the video encodes in the Frame Capture types of output**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output and choose the link for the video encode\.

1. Complete each field as appropriate\. For details about a field, choose the **Info** link next to the field\.

1. When you are ready, go to [save the channel](creating-a-channel-step9.md)\.

## Creating a video encode by sharing<a name="create-video-share"></a>

You can create one video encode and share it among several outputs\. Follow the [earlier procedure](#create-video-scratch) to create the encode once\. Then set up the encode for the other outputs using the following steps\.

Note that the procedure for sharing a video encode is nearly identical to the procedure for sharing an audio encode or captions encode\.

**To create a video encode by sharing**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output where you want to set up a video encode\.

1. If the output already contains a video encode, choose that video and then choose **Remove video**\.

1. Choose **Add video**\. A menu appears that includes the option **Use an existing video description**, followed by a list of the videos that currently exist in the entire channel\.

1. Choose the video that you want to use\. On the dialog that appears, choose **Share the existing settings**\.

   The fields for this encode appear\. Above the first field is an information message that lists all the outputs that share this encode\. 

   You might want to change the video description to include the term *shared*, as a reminder to yourself\.

   Keep in mind that there is only one instance of this encode in the channel\. Therefore, if you change a field, you will change the field in all the other outputs that use this encode\. 

   Remember this rule if you change the **Video selector name** field\. If you specify a different selector in the encode in one output, you change it in all the outputs that share this encode\. If you actually want to specify a different selector, you might need to clone the encode instead of sharing it\.

## Creating a video encode by cloning<a name="create-video-clone"></a>

You can create one video encode and clone it among several outputs\. The *source* encode could be an encode that you created from scratch, or it could be an encode that was itself created by cloning\. For example, create *video\-1*, then clone it to *video\-2*, then clone *video\-2* to *video\-3*\.

Note that the procedure for cloning a video encode is nearly identical to the procedure for cloning an audio encode or captions encode\.

**To create a video encode by cloning**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output where you want to set up a video encode\.

1. If there is a **Video** button on the left, choose that button and then choose **Remove video**\.

1. Choose **Add video**\. A menu appears that includes the option **Use an existing video description**, followed by a list of the videos that currently exist in the entire channel\.

1. Choose the video encode that you want to use as the source for the new video encode\. 

1. On the dialog that appears, choose **Clone the existing settings**\. The fields for the encode appear, with the fields showing the values from the source encode\.

1. Change any fields, as appropriate\.

   Keep in mind that this cloned encode is a new encode instance\. If you change fields, you don't affect the source encode\.