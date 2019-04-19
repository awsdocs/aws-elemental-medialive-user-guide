# Monitoring a Channel Using the AWS Elemental MediaLive Console<a name="monitoring-console"></a>

You can view the activity of your channel and its current state\.

**To monitor activity on a channel \(AWS Elemental MediaLive console\)**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\. 

1. In the navigation pane, choose **Channels**\. \(For information about the buttons on the page, see [Editing a Channel](editing-deleting-channel.md#editing-a-channel), [Starting, Stopping, and Pausing an AWS Elemental MediaLive Channel](starting-stopping-deleting-a-channel.md), and [Creating a Channel by Cloning](creating-channel-clone.md)\.\)

1. The **Channels** page shows a list of your channels\. Each line in the list provides basic information about the channel, including its state:
   + **Creating**\.
   + **Deleting**\.
   + **Idle**: The channel isn't running\. For information about charges that you accrue when a channel is idle, see [Pricing](pricing.md)\.
   + **Recovering**: One or both pipelines in the channel failed, but MediaLive is restarting it\. 
   + **Running**\.
   + **Starting**\.
   + **Stopping**\.
   + **Updating**: You modified a channel, and MediaLive is updating the channel information\.

1. To view more details about a channel, choose the name of that channel\. The **Channel details** page appears\.

## Viewing Status Information<a name="view-status-info"></a>

For basic status information, look at the **Status** pane\.

For information about the inputs in the channel, choose the **Details** tab\.

For detailed information about the status, choose the **Health** tab\. This tab provides information for the pipelines in the channel: 
+ Pipeline 0 and pipeline 1, if the channel is set up as a standard channel and therefore has two pipelines
+ Pipeline 0, if the channel is set up as a single\-pipeline channel

You can specify the period of time for the health information\.

## Viewing Alerts<a name="view-alerts"></a>

AWS Elemental MediaLive generates alerts for a channel when an issue or potential issue occurs in either pipeline in a channel\. These alerts are displayed in two ways:
+ On the right side of the **Status** pane, there is a count of active alerts for each pipeline\. 
+ On the **Alerts** tab, details about each alert are displayed\. 

  If the alert is still active, the **Cleared** column is blank\. If the alert has cleared, the column shows the timestamp for when it cleared\.

## Handling Alerts<a name="handle-alerts"></a>

When an alert occurs, look at the **Alerts** tab to determine possible causes of the issue\. Take steps to resolve the issue\. 

After you resolve the issue, AWS Elemental MediaLive automatically clears the alert\. 

If you stop a channel, alerts always automatically clear\.