# Editing multiplexes, programs, and channels<a name="edit-multiplex-program-channel"></a>

You can edit a multiplex, the programs in a multiplex, and the channels in a multiplex\. There are specific rules that are based on the state \(running or idle\) of the item that you want to work with, as described in this section\. 

## Editing a multiplex<a name="edit-multiplex"></a>

There are very few restrictions on your ability to edit a multiplex\. You can edit a multiplex when these situations apply: 
+ While the multiplex is idle or running, unless you want to change the **Maximum Video Buffer Delay** field\. To change that field, the multiplex must be idle\. 
+ While the channels in the multiplex programs are idle or running\. 
+ While MediaLive is in the process of adding programs that you just created\. 

**To edit a multiplex**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Multiplexes**, and then choose the multiplex that you want to edit\. 

1. On the **Details** pane, choose **Multiplex actions**, and then choose **Edit**\. 

1. Make the changes that you want, and then choose **Save changes**\.

## Editing a program<a name="edit-program"></a>

You can edit a program at any time, including when the multiplex if running or when the associated channel is running\. 

**To edit a program**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Multiplexes**, and then choose the multiplex that you want to edit\. 

1. On the **Details** pane, choose the **Programs** tab\. 

1. Choose **Program actions**, and then choose **Edit**\. 

1. Make the changes that you want, and then choose **Save changes**\. 

## Editing a channel in a program<a name="edit-a-multiplex-channel"></a>

You can edit a channel that is idle\.

**To edit a channel**

1. Stop the channel\. You can stop the channel in the usual way, from the **Channels** pane\. Or you can stop it from the **Multiplex** page\. For more information, see [Stopping a channel in a multiplex](stop-multiplex.title.md#multiplex-channel-stopping)\. 

1. Edit the channel\. For more information, see [Editing a channel](editing-deleting-channel.md#editing-a-channel)\. 