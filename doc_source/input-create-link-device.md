# Creating an Elemental Link input<a name="input-create-link-device"></a>

Create your input before you create the channel that ingests the input\. 

You create an Elemental Link input by attaching a MediaLive device to the input\. This device is the representation within MediaLive of the AWS Elemental Link hardware device\.

You can set up an Elemental Link input as single\-class or a standard\-class input\. You should have already read [Implementing pipeline redundancy](plan-redundancy-mode.md), to decide the class of channel and class of input you want 

To set up a single\-class input, you attach one MediaLive device to the input\. To set up a standard\-class input, you attach two different MediaLive devices to the input\.

**To create a Link input**

1. You should have already arranged with the AWS Elemental Link operator to [provide one or two AWS Elemental Link hardware devices](hls-upstream.md#setup-hls-obtain-info) with your content\. Make sure that the AWS Elemental Link operator gives you the following information:
   + The name of the AWS Elemental Link device or devices that are providing the source for the input\. For example:

     **hd\-re87jr7crey**

     **hd\-18zel9mimi**
   + The AWS Region where the AWS Elemental Link devices are configured to work\. 

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. Set the AWS Region to match the Region where the MediaLive device exists\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. Complete the **Input details** section:
   + **Input** name – enter a name\.
   + **Input type** – choose **Elemental Link**\. 

1. In the **Input devices** section, for **Input class**, choose the class for this input:
   + STANDARD\_INPUT
   + SINGLE\_INPUT

1. In **Input devices**, choose one or two devices to attach to this input as the source\. From the dropdown lists, choose the device names you previously obtained\. The lists show only the devices that are set up in the current Region\.
   + If the input is a standard\-class input, complete both fields, to provide two source devices\. 
   + If the input is a single\-class input, complete the first field and leave the second field empty\. 

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive resources](tagging.md)\.

1. Choose **Create**\.

   The **Details** pane appears for the input, showing details about the input and the MediaLive device that it uses, including the following:
   + **ID** – A unique numerical ID for the input\.
   + **ARN** – An input ARN that includes that numerical ID\. 
   + **Input device** – The unique ID of the AWS Elemental Link device\.
   + **Device thumbnail** – A thumbnail of the content that is currently being pushed by the device, if there is any being pushed\. The device generates the thumbnails by capturing a video frame approximately every 5 seconds\.