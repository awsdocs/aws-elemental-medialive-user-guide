# Viewing the Schedule \(Console\)<a name="schedule-using-console-view"></a>

You can display the list of actions currently in the schedule and view them in list or timeline view\.

**To view actions \(console\)**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channel**, and then choose the channel that you want to work with\.

1. On the **Details** pane, choose the **Schedule** tab\.

   The **Schedule actions** pane shows the actions in the schedule's current window of time\. 

   You can switch between the two views of the schedule by choosing the **Switch** button\. 

**List View**  
The actions are mostly listed in chronological order\.

Input switches in a follow chain are grouped together starting from the top of the chain \(which is the action above the first follow action\) to the last follow action\. Other actions, such as actions for SCTE\-35 and image overlay, might occur between two follow actions\. MediaLive can't predict whether a SCTE\-35 or image overlay action will occur between two follow actions and doesn't attempt to show it in the list view\. 

**Timeline View**  
The actions are arranged in cards along a vertical axis\. The card titles are color\-coded by the action type\. For example, SCTE\-35 time\_signal messages are yellow\.

One card might contain several input switches\. The first input switch is always a fixed input switch, and the remaining input switches in that card are always follow input switches\.

**Window of Time for the Schedule**  
The searchable window of time for the schedule extends to approximately one hour in the past\. Actions with a start time more than one hour in the past aren't displayed when you view the schedule on the console, and aren't included in the response to a `DescribeChannel` command\.

However, a running action that is no longer visible continues to run for its full duration\. 

The existence of this searchable window of time means the following:
+ Actions that relate to SCTE\-35: for messages that have a duration \(splice\_insert specified with a duration\), the message could still be active, but it is no longer possible to query MediaLive for the duration\. 
+ Actions that relate to image overlays: for actions to activate a static image overlay for a duration of time, the overlay might still be active, but it is no longer be possible to query MediaLive for the duration\.
+ Actions that relate to input switching: there is no impact\.
+ Actions that relate to ID3 metadata: there is no impact\.