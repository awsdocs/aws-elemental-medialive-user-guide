# Editing or viewing details for a MediaLive device<a name="device-edit"></a>

You can fine\-tune the setup of the MediaLive device in the following ways:
+ Give the device a friendly name
+ Edit the device to throttle the delivery bitrate
+ Edit the device to use a specific source

You can also view all the settings for the connection between MediaLive and AWS Elemental Link\.

**To edit or view an input**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Devices**\.

1. In **Devices**, go to the card for the MediaLive device that you want, and choose the hyperlink\. If there are many MediaLive devices, enter part of the name to filter the list\.

1. The details page for this MediaLive device shows information about the device, including the following:
   + The unique ID of the AWS Elemental Link hardware \(displayed at the top of the page\)\.
   + A thumbnail of the content that is currently being pushed by the device, if there is any being pushed\. The device generates the thumbnails by capturing a video frame approximately every 5 seconds\.
   + The [status of the connection](device-status.md) to the AWS Elemental Link hardware\. 
   + A device ARN that includes that unique ID\.

1. \(Optional\) On the **Device** page, choose **Edit**\.

1. Change any field as needed: 
   + **Name** – Enter a name for the device\. This name supplements the generated name \(such as hd\-re87jr7crey\)\.

     We recommend that you include a prefix in the name—**hd\-** to indicate that this is an HD device\.
   + **Input source** – This field configures the AWS Elemental Link hardware for which content to send—SDI content or HDMI content\. The AWS Elemental Link hardware can receive content at an SDI port and an HDMI port\. Typically, in a production environment, the device receives content at only one port\. Therefore, you can set this field to **Auto**\. In some situations, the operator of the AWS Elemental Link hardware might instruct you to set this field to **SDI** or **HDMI**\.
   + **Maximum bitrate** – Enter a bitrate in bits/sec only if you want to throttle the bitrate that AWS Elemental Link uses to deliver the stream\. Leave this field blank to let AWS Elemental Link determine the bitrate that is best for the network conditions between the hardware device and MediaLive\.

1. Choose **Update**\.

   Wait for the input **State** to return to **In use** or **Idle** before performing another action with this input\.

The new values appear in **Active input** and **Max bitrate** in the **Device settings**\. MediaLive sends the new values for these settings to AWS Elemental Link, so that AWS Elemental Link can update itself\.