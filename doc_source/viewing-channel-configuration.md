# Viewing a Channel Configuration<a name="viewing-channel-configuration"></a>

You can view information about the configuration of a channel on the **Channel details** page on the AWS Elemental MediaLive console\. This page is useful for viewing information when the channel is running\. \(When a channel is running, you can't view details by choosing **Edit**\)\. 

**To view configuration information \(AWS Elemental MediaLive console\)**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channels**\. \(For information about the buttons on this page, see [Editing a Channel](editing-deleting-channel.md#editing-a-channel), [Starting, Stopping, and Pausing an AWS Elemental MediaLive Channel](starting-stopping-deleting-a-channel.md), and [Creating a Channel by Cloning](creating-channel-clone.md)\.\)

1. To view more details about a channel, choose the name of that channel\. The **Channel details** page appears\. 

1. View configuration information in one of these places:
   + For information about the input specification for the channel, choose the **Details** tab and look at the **Input specifications** pane\.
   + For a one\-click view of the destination for the channel \(on the downstream system\), choose the **Destinations** tab\.
   + For basic information about the configuration of the channel, choose the **Details** tab\. 
   + For a read\-only view of the complete configuration of the channel \(which you specified when you created or edited the channel\), choose the **Settings** tab\.
   + For a view of the raw JSON code for the channel configuration, choose the **Details** tab, and then choose **Advanced** details\. You can copy this JSON code to your clipboard\.