# Deleting Actions from the Schedule \(Console\)<a name="schedule-using-console-delete"></a>

You can delete actions that you previously created in the schedule, so long as the action has not been received by the channel\. You can delete an action when the channel is running or when it is idle\. 

The action that you delete must have a UTC start time or a follow start time \(for input switches\) that is at least 15 seconds in the future\. \(In other words, it must not be already received in the channel\.\) After that cutoff, AWS Elemental MediaLive rejects the delete request\.

You can delete any number of actions in one request, or any combination of types of actions in one request\. For example, you can mix the deletion of SCTE\-35 message actions and image overlay actions\.

The general procedure is the same to delete any type of action\.

**To delete actions in List view**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channel**, and then choose the channel that you want to work with\.

1. On the **Details** pane, choose the **Schedule** tab\.

1. If necessary, choose the **Switch** button to display the **List** view\. For information about the layout and color coding of the timeline view, see [Viewing the Schedule \(Console\)](schedule-using-console-view.md)\.

1. Choose one or more actions to delete\. Make sure that you choose actions with a UTC start time in the future\.

   If you choose an input switch that is in a follow chain, a prompt appears to notify you that the follow actions below this action \(up to the next fixed input switch\) will also be deleted\. You can cancel or continue\. 

   Choose **Actions**, and then choose **Delete**\.

**To delete actions in Timeline view \(console\)**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channel**, and then choose the channel that you want to work with\.

1. On the **Details** pane, choose the **Schedule** tab\.

1. If necessary, choose the **Switch** button to display the **Timeline** view\. For information about the layout and color coding of the timeline view, see [Viewing the Schedule \(Console\)](schedule-using-console-view.md)\.

1. In each action section, choose the **X** to delete the action\. Make sure that you choose actions with a UTC start time in the future\.

   If you choose an input switch that is in a follow chain, a prompt appears to notify you that the follow actions below this action \(up to the next fixed input switch\) will also be deleted\. You can cancel or continue\. 