# Viewing the schedule \(console\)<a name="schedule-using-console-view"></a>

You can display the list of actions currently in the schedule and view them in list or timeline view\.

**To view actions \(console\)**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channel**, and then choose the channel that you want to work with\.

1. On the **Details** pane, choose the **Schedule** tab\.

   The **Schedule actions** pane shows the actions in the schedule's current window of time\. 

   You can switch between the two views of the schedule by choosing the **Switch** button\. 

**List view**  
The actions are mostly listed in chronological order\.

Input switches in an input follow chain are grouped together starting from the top of the chain \(which is the action above the first follow action\) to the last follow action\. Other actions, such as actions for SCTE\-35 and image overlay, might occur between two follow actions\. MediaLive can't predict whether a SCTE\-35 or image overlay action will occur between two follow actions and doesn't attempt to show it in the list view\. 

**Timeline view**  
The actions are arranged in cards along a vertical axis\. The card titles are color\-coded by the action type\. For example, SCTE\-35 time\_signal messages are yellow\.

One card might contain several input switches\. The first input switch is always a fixed\-type input switch\. The remaining input switches in that card are always follow\-type input switches\.