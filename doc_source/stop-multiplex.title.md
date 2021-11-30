# Stopping activity in the multiplex<a name="stop-multiplex.title"></a>

You can stop a multiplex or a channel\. 

## Stopping a multiplex<a name="multiplex-stop"></a>

Typically, after your multiplex is in a production environment, you stop the multiplex only to delete it\. You don't need to stop the multiplex to modify it, except to modify the **Maximum Video Buffer Delay** field\. 

When you stop a multiplex, the channels continue to run, although their outputs are not with an MPTS, so the outputs don't go to their destinations\. 

When you stop a multiplex, you stop accruing charges for the multiplex\. But you still accrue charges for the channels in the multiplex, unless you also stop those channels\. 

**To stop a multiplex**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Multiplexes**, and then choose the multiplex that you want to stop\.

1. On the **Details** pane, choose **Multiplex actions**, and then choose **Stop multiplex**\. If there are programs and those programs have running channels, then the channels continue to run, although their outputs don't go to their destinations\. 

## Stopping a channel in a multiplex<a name="multiplex-channel-stopping"></a>

You must stop a channel to change its configuration or to delete it\. 

When you stop a channel, the multiplex continues to run\. MediaLive modifies the PMT to remove the PAT for the associated program\. 

When you stop a channel, you stop accruing charges for the channel\. But you still accrue charges for the multiplex, unless you also stop the multiplex\. You should review the charges for a running multiplex; you might consider that there is not a lot of gain in stopping the multiplex\. 

**To stop a channel**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Multiplexes**, and then choose the program for the channel\. 

1. On the **Programs** pane, choose the program or programs, choose **Multiplex actions**, and then choose **Stop channel**\. 

You can also stop a channel in the multiplex in the same way as you stop a regular channel\. For more information, see [Starting, stopping, and pausing an AWS Elemental MediaLive channel](starting-stopping-deleting-a-channel.md)\.