# Editing and deleting a channel<a name="editing-deleting-channel"></a>

You can edit an existing \(saved\) channel to change how it processes the input, and you can delete a channel\. However, you can edit or delete a channel only when it is not running\.

## Editing a channel<a name="editing-a-channel"></a>

You can edit any existing channel by editing, adding, or deleting output groups and outputs\. you can also edit, add, or delete the channel's video, audio, and caption encodes\.

The channel must be idle \(not running\)\.

**Note**  
You can't change the class for a channel by editing the channel\. Instead, see [Update the channel class—pipeline redundancy](edit-channel-class.md)\.

**To edit a channel**

1. On the **channels** page, choose the option by the channel name\.

1. Choose actions, and then choose **edit**\. The edit channel page appears\. The details on this page are identical to those on the **create channel** page\. For information about working with this page, see [Creating a channel from scratch](creating-channel-scratch.md)\.

1. When done, choose update channel\. 

   Wait for the channel **state** to return to **idle** before performing another action with this channel\. 

## Editing the tags associated with a channel<a name="edit-channel-tags"></a>

You can edit the tags associated with a channel at any time, when the channel is running or when it is idle\. You can add more tags \(up to the [limit](tagging.md#tagging-restrictions)\), and you can delete tags\.

**To edit the tags in a channel**

1. On the **Channels** page, choose the channel name\.

1. Choose the Tags tab\. Add or delete tags\. To edit the value of an existing tag, delete the tag and add it again\. For more information, see [Tagging AWS Elemental MediaLive resources](tagging.md)\. 

1. When done, choose Save\. 

## Deleting a channel<a name="deleting-a-channel"></a>

You can delete a channel from the **Channels** list or the details view\. 

The channel must be idle \(not running\)\.

**To delete a channel**

1. On the **Channels** page, choose the option by the channel name\.

1. If the channel is running, choose **Stop**\. 

1. Choose **Delete**\.