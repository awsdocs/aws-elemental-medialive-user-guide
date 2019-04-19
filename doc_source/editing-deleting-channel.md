# Editing and Deleting a Channel<a name="editing-deleting-channel"></a>

You can edit an existing \(saved\) channel to change how it processes the input, and you can delete a channel\. However, you can edit or delete a channel only when it is not running\.

## Editing a Channel<a name="editing-a-channel"></a>

You can edit any existing channel by editing, adding, or deleting output groups and outputs\. You can also edit, add, or delete the channel's video, audio, and caption encodes\.

The channel must be idle \(not running\)\.

**Note**  
You can't edit a channel to change the input associated with that channel\. Instead, you must [clone ](creating-channel-clone.md) the channel and associate a different input\.

**To edit a channel**

1. On the **Channels** page, choose the option by the channel name\.

1. Choose Actions, and then choose **Edit**\. The Edit channel page appears\. The details on this page are identical to those on the **Create channel** page\. For information about working with this page, see [Creating a Channel from Scratch](creating-channel-scratch.md)\.

1. When done, choose Update channel\. 

   Wait for the channel **State** to return to **Idle** before performing another action with this channel\. 

## Editing the Tags Associated with a Channel<a name="edit-channel-tags"></a>

You can edit the tags associated with a channel at any time, when the channel is running or when it is idle\. You can add more tags \(up to the [limit](tagging.md#tagging-restrictions)\), and you can delete tags\.

**To edit the tags in a channel**

1. On the **Channels** page, choose the channel name\.

1. Choose the Tags tab\. Add or delete tags\. To edit the value of an existing tag, delete the tag and add it again\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\. 

1. When done, choose Save\. 

## Deleting a Channel<a name="deleting-a-channel"></a>

You can delete a channel from the **Channels** list or the details view\. 

The channel must be idle \(not running\)\.

**To delete a channel**

1. On the **Channels** page, choose the option by the channel name\.

1. If the channel is running, choose **Stop**\. 

1. Choose **Delete**\.