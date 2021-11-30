# Getting ready: Set the ad avail mode<a name="getting-ready-set-the-ad-avail-mode"></a>

You must set the Ad Avail mode to notify MediaLive of the ID type of SCTE\-35 messages that the input is using to indicate ad avail events\.

**To set the ad avail mode**

1. In the channel that you are creating, in the navigation pane, choose **General settings**\. 

1. Choose **Avail configuration**\.

1. Set the **Avail settings**: 
   + SCTE\-35 splice insert \(default\): Select this mode if the input uses splice inserts to indicate ad avails\. The input might also contain messages for others events such as chapters or programs\. 
   + SCTE\-35 time signal apos: Select this mode if the input contains time signals of segmentation type **Placement opportunity**\. The input might also contain messages for other events such as chapters or programs\. 

1. In **Ad avail offset**, set a value, if desired\. For details about a field on the MediaLive console, choose the **Info** link next to the field\.

1. Leave **web\_delivery\_allowed\_flag** and **no\_regional\_blackout\_flag** as Follow for now\. For information about these fields, see [Ad avail blanking restriction flags](ad-avail-blanking-restriction-flags.md)\. 