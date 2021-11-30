# Step 2: Setting up for pipeline locking<a name="pipeline-locking-set-up"></a>

Pipeline locking is always enabled\. But you must set up the channel to make sure that MediaLive can successfully perform pipeline locking in your output groups\.

**Note**  
All the procedures in this section assume that you are familiar with the general steps for creating a channel, as described [Creating a channel from scratch](creating-channel-scratch.md)\.

## Setting the mode and timecode for pipeline locking<a name="pipeline-locking-mode"></a>

**Configure the pipeline locking mode**

1. In the channel that you are creating, in the navigation pane, choose **General settings**\. Then choose **Global configuration**\.

1. Choose **Enable global configuration**\.

1. In **Output locking mode**, choose the mode—pipeline\_locking or epoch\_locking\. For details about the options, choose the **Info** link next to the field\.

1. In the **General settings** section, choose **Timecode configuration**\. Set **Source** to **Embedded**\. You must set this field, otherwise MediaLive won't attempt to perform pipeline locking\.

   You can optionally set the **Sync threshold**\. This field has no effect on pipeline locking\.

## Setting up an HLS, MediaPackage, or Microsoft Smooth output group<a name="pipeline-locking-outputgroups"></a>

In an HLS output group or Microsoft Smooth output group, you must set up the framerate for each video encode\. 

**Set up for pipeline locking**

1. In the channel that you are creating, in the navigation pane, choose the HLS or Microsoft Smooth output group\.

1. If necessary, create the outputs and video encodes in each output, then choose the first video encode\.

1. In the **Codec settings** field, choose the codec\. More fields appear\.

1. Choose the **Frame rate ** section and set the following fields:
   + **Framerate control**: We recommend you choose **Specified**\. The option **Initialize\_from\_source** doesn't work well with pipeline locking\.
   + **Framerate numerator** and **Framerate denominator**: Set the desired resolution for the output\. Make sure that the conversion from input framerate to output framerate meets [the requirements](pipeline-locking-verify-input.md)\.

1. Continue setting up the channel\.

## Setting up a UDP output group<a name="pipeline-locking-udp"></a>

In a UDP output group, you must obtain information about segmentation markers, and set up the segmentation markers for framerate for each video encode\.

**Set up for pipeline locking**

1. You need information about the how to configure segmentation in the outputs\. This information is contained in fields on the **Create channel** page on the console\. To display the fields, in the navigation pane choose **Archive group**\. Then choose an output and choose **Network settings**\. Choose the **Info** link next to each of the following fields: 
   + **Segmentation markers**
   + **Segmentation time**
   + **EBP lookahead msec**
   + **Fragment time**
   + **Segmentation style**
   + **EBP placement**
   + **EBP audio interval**

1. Speak to your contact at the downstream system to obtain recommended values for these fields\. 

1. In the channel that you are creating, in the navigation pane, choose the Archive output group\.

1. If necessary, create the outputs\. Then in the **Output settings**, choose **Network settings**\. More fields appear\.

1. Choose **Container settings** and set values for the segmentation fields listed in step 1\. It's possible that some of the fields don't apply to the segmentation markers you choose\.

1. If necessary, create the video encodes in each output, then choose the first video encode\.

1. In the **Codec settings** field, choose the codec\. More fields appear\.

1. Choose the **Frame rate ** section and set the following fields:
   + **Framerate control**: We recommend you choose **Specified**\. The option **Initialize\_from\_source** doesn't work well with pipeline locking\.
   + **Framerate numerator** and **Framerate denominator**: Set the desired framerate for the output\. Make sure that the conversion from input framerate to output framerate meets [the requirements](pipeline-locking-verify-input.md)\.

1. Continue setting up the channel\.