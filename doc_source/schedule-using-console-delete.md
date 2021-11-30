# Deleting actions from the schedule \(console\)<a name="schedule-using-console-delete"></a>

These rule apply when you add delete actions to the schedule:
+ In a single\-input channel \(a channel that doesn't involve input switching\), you can delete actions as follows: 
  + You can delete an action with a start time that is more than 15 seconds in the future\. The channel won't perform the action\.
  + You can delete an action that has already been performed\. Deleting this action doesn't reverse the action, it only removes it from the schedule\.
+ In a multiple\-input channel, you can delete actions as follows:
  + You can delete an action with a start time that is more than 15 seconds in the future\. The channel won't perform the action\.

    There are some constraints that apply to deleting inputs switches and input prepare, event when they are in the future\. For more information, see [Deleting actions from the schedule](ips-manage-schedule.md) and [Deleting and stopping input prepare actions](input-prep-delete.md)\.
  + You can delete an action that has already been performed\. Deleting this action doesn't reverse the action, it only removes it from the schedule\.

    There are some constraints that apply to deleting inputs switches and input prepare, event when they are in the future\. For more information, see [Deleting actions from the schedule](ips-manage-schedule.md) and [Deleting and stopping input prepare actions](input-prep-delete.md)\.

**Deleting versus reversing**

It is important to understand that deleting a stale action from the schedule doesn't reverse its effect in the channel\. For example, if you have paused the channel, and the channel has performed the action, you unpause the channel by entering a new action\. You don't unpause it by deleting the action\.

**Note**  
If the channel has already received the action, you might be able to modify it to effectively delete it\. For more information, see [Modifying actions in the schedule \(console\)](schedule-modify.md)\.

You can delete any number of actions in one request, or any combination of types of actions in one request\. For example, you can mix the deletion of SCTE\-35 message actions and image overlay actions\.

The general procedure is the same to delete any type of action\.

**To delete actions in list view**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channel**, and then choose the channel that you want to work with\.

1. On the **Details** pane, choose the **Schedule** tab\.

1. If necessary, choose the **Switch** button to display the **List** view\. For information about the layout and color coding of the timeline view, see [Viewing the schedule \(console\)](schedule-using-console-view.md)\.

1. Choose one or more actions to delete\.

   If you choose an input switch that is in an input follow chain, a prompt appears\. This prompt notifies you that all the follow input switch actions and the follow SCTE\-35 actions up to the next fixed input switch will also be deleted\. You can cancel or continue\. 

   Choose **Actions**, and then choose **Delete**\.

**To delete actions in timeline view \(console\)**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channel**, and then choose the channel that you want to work with\.

1. On the **Details** pane, choose the **Schedule** tab\.

1. If necessary, choose the **Switch** button to display the **Timeline** view\. For information about the layout and color coding of the timeline view, see [Viewing the schedule \(console\)](schedule-using-console-view.md)\.

1. In each action section, choose the **X** to delete the action\.

   If you choose an input switch that is in an input follow chain, a prompt appears to notify you that the follow actions below this action \(up to the next fixed input switch\) will also be deleted\. You can cancel or continue\. 