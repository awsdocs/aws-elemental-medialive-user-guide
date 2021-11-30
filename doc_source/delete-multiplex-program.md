# Deleting multiplexes, programs, and channels<a name="delete-multiplex-program"></a>

You can delete a multiplex, the programs in a multiplex, and the channels in a multiplex\. There are specific rules that are based on the state of the item that you want to work with, as described in this section\. 

## Deleting a multiplex<a name="delete-multiplex"></a>

To delete a multiplex, the multiplex must be idle, and all of its programs must be empty \(they must not have associated channels\.\) 

**To delete a multiplex**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Multiplexes**, and then choose the multiplex that you want to delete\. 

1. On the **Details** pane, choose **Multiplex actions**, and then choose **Stop**\. 

1. On the **Programs** pane, choose the first program with a running channel, choose **Program actions**, and then choose **Stop channel**\. 

1. Repeat for all the channels that are running\. 

1. Make a note of the names of the channels, and then display the **Channels** page\. Choose the channels, choose **Actions**, and then choose **Delete**\. 

1. Return to the **Multiplex** page\. 

1. Choose **Multiplex actions**, and then choose **Delete multiplex**\. MediaLive deletes the multiplex and all of its programs\. 

## Deleting a program<a name="delete-program"></a>

You can delete a program that has no channel\. You can delete a program when the multiplex is running or idle\. 

**To delete a program**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Multiplexes**, and then choose the multiplex that you want to work with\. 

1. On the **Programs** pane, choose the program to delete\. 

1. If the channel for that program is running, choose **Program Actions**, and then choose **Stop channel**\. 

1. Wait for the channel to change to **Idle**\. 

1. Make a note of the name of the channel, and then display the **Channels** page\. Choose the channel, choose **Actions**, and then choose **Delete**\. 

1. Return to the **Multiplex** page\. 

1. Choose **Program actions**, and then choose **Delete program**\. 

## Deleting a channel<a name="delete-a-multiplex-channel"></a>

You can delete a channel when the multiplex is running or idle\. You don’t detach the channel from its program—there is no concept of detaching a channel from a program\. 

To delete a channel, display the **Channel** page, and delete the channel in the usual way\. For more information, see [Deleting a channel](editing-deleting-channel.md#deleting-a-channel)\. 