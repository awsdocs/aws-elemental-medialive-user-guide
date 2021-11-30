# Starting, stopping, and pausing an AWS Elemental MediaLive channel<a name="starting-stopping-deleting-a-channel"></a>

After you create a channel, you can start it\. The channel never starts automatically except when it is already running and attempts to recover from a failure\.

You can stop a running channel at any time\. 

You can also pause one or both the pipelines in a channel by adding a Pause action to the schedule for the channel\. For more information, see [How pause and unpause actions work](sched-how-actions-work.md#x-actions-in-schedule-pause)\.

For information about charges for a channel, see [Pricing](pricing.md)\. There are different charges depending on the state of the channel:
+ Charges when the channel is running
+ Charges when the channel is idle

**To start a channel**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channels**, and then on the **Channels** page, choose the channel that you want to start\.

1. Choose **Start**\. The channel state changes to one of the following:
   + **Starting**
   + **Running** \(encoding on the pipeline or pipelines\)

1. Choose the channel name\. The details for the channel appear\.

**To stop a channel**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channels**, and then on the **Channels** page, choose the channel that you want to stop\.

1. Choose **Stop**\.