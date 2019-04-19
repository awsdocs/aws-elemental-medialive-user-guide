# Creating Actions in the Schedule \(Console\)<a name="schedule-using-console-create"></a>

You can create actions to switch the input that the channel is ingesting, activate or deactivate image overlays on the video, insert SCTE\-35 messages in the output, insert ID3 metadata in the output, or pause or unpause a pipeline in the channel\. 

You can create an action in the schedule when the channel is running or when it is idle\.

The action that you create must have a UTC start time or a follow start time \(for input switches\) that is at least 15 seconds in the future\. \(In other words, it must not be already received in the channel\.\) After that cutoff, AWS Elemental MediaLive rejects the create request\.

The general procedure is the same to create any type of action\.

**To create an action**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channel**, and then choose the channel that you want to work with\.

1. On the **Details** pane, choose the **Schedule** tab\.

1. Choose the **Switch** button to display the view that you want: **List** view or **Timeline** view\. For information about the layout and color coding of the timeline view, see [Viewing the Schedule \(Console\)](schedule-using-console-view.md)\.

1. For **List** view, choose **Create**\. Or choose an existing action, choose **Actions**, and then choose **Create follow actions from**\. This action displays the **Create schedule action** page with some fields already completed, so you can quickly create a follow switch for that existing action\.

1. For **Timeline** view, choose the appropriate action:
   + To create a fixed input switch, an image overlay action, a SCTE\-35 action, or an HLS timed metadata \(ID3 metadata\) action, choose **Create**\.
   + To create a follow input switch, find the action for the preceding input switch, and then choose **Create follow action** in that card\.

1. On the **Create schedule action** page, complete the fields\. For information about completing the fields, see the following topics\.

1. When you are done, choose **Create**\.

   MediaLive adds the action to the list or the timeline at its appropriate time slot\. 

When you create a follow input switch, you effectively create a *follow chain*\. The follow chain starts with the input above the first follow and ends with the last follow input\. For more information about follow chains, see [Types of Switches—Fixed, Follow, and Follow Chains](ips-switch-types.md)\.

**Topics**
+ [Fields for an Input Switch](schedule-fields-for-ips.md)
+ [Fields for Activating an Image Overlay](schedule-fields-for-activate-image.md)
+ [Fields for Deactivating an Image Overlay](schedule-fields-for-deactivate-image.md)
+ [Fields for a Splice\_Insert Message](schedule-fields-for-splice_insert.md)
+ [Fields for a Time\_Signal Message](schedule-fields-for-time-signal.md)
+ [Fields for a Return\-to\-Network Message](schedule-fields-for-return-to-network.md)
+ [Fields for ID3 Metadata](schedule-fields-for-id3-userdata.md)
+ [Fields for Pause](schedule-fields-for-pause.md)
+ [Fields for Unpause](schedule-fields-for-unpause.md)