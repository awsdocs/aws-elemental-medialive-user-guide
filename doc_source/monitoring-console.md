# Monitoring a channel using the AWS Elemental MediaLive console<a name="monitoring-console"></a>

You can view the activity of your channel and its current state\.

**To monitor activity on a channel \(AWS Elemental MediaLive console\)**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channels**\. \(For information about the buttons on the page, see [Editing a channel](editing-deleting-channel.md#editing-a-channel), [Starting, stopping, and pausing an AWS Elemental MediaLive channel](starting-stopping-deleting-a-channel.md), and [Creating a channel by cloning](creating-channel-clone.md)\.\)

1. The **Channels** page shows a list of your channels\. Each line in the list provides basic information about the channel, including its state:
   + **Creating**
   + **Deleting**
   + **Idle**: The channel isn't running\. For information about charges that you accrue when a channel is idle, see [Pricing](pricing.md)\.
   + **Recovering**: One or both pipelines in the channel failed, but MediaLive is restarting it\. 
   + **Running**\.
   + **Starting**
   + **Stopping**
   + **Updating**: You changed the [channel class](class-channel-input.md)for a channel\. 

   Note that [Amazon CloudWatch events](monitoring-via-cloudwatch.md) also capture state changes except a change to updating\.

1. To view more details about a channel, choose the name of that channel\. The **Channel details** page appears\.

## Status tab – Viewing status information<a name="view-status-info"></a>

For basic status information, look at the **Status** pane\.

For information about the inputs in the channel, choose the **Details** tab\.

For detailed information about the status, choose the **Health** tab\. This tab provides information for the pipelines in the channel: 
+ Pipeline 0 and pipeline 1, if the channel is set up as a standard channel and therefore has two pipelines
+ Pipeline 0, if the channel is set up as a single\-pipeline channel

You can specify the period of time for the health information\.

## Alerts tab – Viewing alerts<a name="view-alerts"></a>

MediaLive generates alerts for a channel when an issue or potential issue occurs in either pipeline in a channel\. These alerts are displayed in two ways:
+ On the right side of the **Status** pane, there is a count of active alerts for each pipeline\. 
+ On the **Alerts** tab, details about each alert are displayed\. 

  If the alert is still active, the **Cleared** column is blank\. If the alert has cleared, the column shows the timestamp for when it cleared\.

## Handling alerts<a name="handle-alerts"></a>

When an alert occurs, look at the **Alerts** tab to determine possible causes of the issue\. Take steps to resolve the issue\. 

After you resolve the issue, MediaLive automatically clears the alert\. 

If you stop a channel, alerts always automatically clear\.

## Destinations pane<a name="view-status-details"></a>

This pane has three panes:
+ **Egress endpoints** – This pane shows one line for each pipeline\. The **Source IP** is the channel endpoint for this pipeline\. The channel endpoint is the egress from the pipeline\. From this point, the content goes to the output destinations for each of the output groups in the channel\. 

  In a regular channel, this endpoint is in a location that MediaLive manages\.

  In a channel set up for [delivery via your VPC](delivery-out-vpc.md), this endpoint is in your VPC\. You are responsible for ensuring that this endpoint is always available to accept the content from the channel pipeline\.
+ **Destinations** – This pane shows one line for each destination\. 

  Each output group has one destination line\. Each line shows the address of the output in the one or two pipelines in the channel\.
+ **MediaPackage destinations** – This pane shows the channel ID that is the destination for each MediaPackage output group\. The channel in MediaPackage has one or two pipelines, mapped to the one or two pipelines in MediaLive\.