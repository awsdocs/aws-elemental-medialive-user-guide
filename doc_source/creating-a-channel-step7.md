# Step 7: Set up the audio encodes<a name="creating-a-channel-step7"></a>

In [Step 5: Create output groups and outputs](creating-a-channel-step4.md), you created the output groups and outputs that you identified when you planned the channel\. Each output section contains a **Stream settings** section\. You must now create the audio [encodes](channels.md#encode) for the outputs\. 

**General procedure**  
Follow this general procedure to set up the audio encode\.

1. Decide how you're going to create each encode:
   + From scratch\.
   + By sharing an encode that already exists in this output or another output in the channel\.
   + By cloning an encode that already exists in this output or another output in the channel\.

   You might have already made this decision\. If not, you should decide now\. For more information, see [Step 4: Design the encodes](designing-encodes.md)\.

   You can share or clone audio encodes within one output, from one output to another in the same output group, or from one output to an output in another output group\.

1. Read the appropriate sections that follow\.

**Topics**
+ [Creating an audio encode from scratch](#create-audio-scratch)
+ [Creating an audio encode by sharing](#create-audio-share)
+ [Creating an audio encode by cloning](#create-audio-clone)

## Creating an audio encode from scratch<a name="create-audio-scratch"></a>

**To set up the audio encodes from scratch**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output where you want to set up an audio encode\.

1. If you need to add a new audio to this output, choose **Add audio**, then choose **Create a new audio description**,

1. Choose the audio encode, and in **Codec settings**, choose the codec to use for this encode\. More fields appear\.

1. In **Audio selector name**, choose the selector that is the source for this audio encode, according to [your plan](channel-map-output-source.md)\. You [created this selector](input-audio-selectors.md) earlier\.

1. Complete other fields as appropriate\. For details about a field, choose the **Info** link next to the field\. 
   + The fields in the **Codec settings** section are different for each type of codec\.
   + The fields in the **Remix settings** section are optional\.
   + The fields in the **Audio normalization** settings are optional\.
   + The fields in the **Additional settings** section are optional\.

## Creating an audio encode by sharing<a name="create-audio-share"></a>

You can create one audio encode and share it among several outputs\. Follow the [earlier procedure](#create-audio-scratch) to create the encode once\. Then set up the encode for the other outputs using the following steps\.

Note that the procedure for sharing an audio encode is nearly identical to the procedure for sharing a video encode or captions encode\.

**To create an audio encode by sharing**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output where you want to set up an audio encode\.

1. The output might contain an audio encode that MediaLive has automatically added\. If you don't plan to use this audio encode, remove it\. Choose the audio encode and choose **Remove audio**\.

1. Create a new audio\. Choose **Add audio**\. A menu appears that includes the option **Use an existing audio description**, followed by a list of the audios that currently exist in the entire channel\. Choose the audio that you want to use\.

1. On the dialog that appears, choose **Share the existing settings**\.

   The fields for this encode appear\. Above the first field is an information message that lists all the outputs that share this encode\. 

   You might want to change the audio description to include the term *shared*, as a reminder to yourself\.

   Keep in mind that there is only one instance of this encode in the channel\. Therefore, if you change a field, you will change the field in all the other outputs that use this encode\. 

   Remember this rule if you change the **Audio selector name** field\. If you specify a different selector in the encode in one output, you change it in all the outputs that share this encode\. If you actually want to specify a different selector, you might need to clone the encode instead of sharing it\.

## Creating an audio encode by cloning<a name="create-audio-clone"></a>

You can create one audio encode and clone it among several outputs\. The *source* encode could be an encode that you created from scratch, or it could be an encode that was itself created by cloning\. For example, create *audio\-1*, then clone it to *audio\-2*, then clone *audio\-2* to *audio\-3*\.

Note that the procedure for cloning an audio encode is nearly identical to the procedure for cloningg a video encode or captions encode\.

**To create an audio encode by cloning**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output where you want to set up an audio encode\.

1. The output might contain an audio encode that MediaLive has automatically added\. If you don't plan to use this audio encode, remove it\. Choose the audio encode and choose **Remove audio**\.

1. Create a new audio\. Choose **Add audio**\. A menu appears that includes the option **Use an existing audio description**, followed by a list of the audios that currently exist in the entire channel\. Choose the audio that you want to use\.

1. Choose the audio encode that you want to use as the source for the new audio encode\.

1. On the dialog that appears, choose **Clone the existing settings**\. The fields for the encode appear, with the fields showing the values from the source encode\.

1. Change any fields, as appropriate\.

   Keep in mind that this cloned encode is a new encode instance\. If you change fields, you don't affect the source encode\.