# Getting Ready: Set the Ad Avail Mode<a name="getting-ready-set-the-ad-avail-mode"></a>

You must set the Ad Avail mode to notify MediaLive of the ID type of SCTE\-35 messages that the input is using to indicate ad avail events\.

Follow this procedure if you want to support one or more of the following features:
+ Manifest decoration
+ Ad avail blanking

If your processing does not involve at least one of these features, the ad avail mode is ignored\.

**To set the ad avail mode**

1. In the channel that you are creating, in the navigation pane, choose **General settings**\. 

1. Choose **Avail configuration**\.

1. Set the **Avail settings**: 
   + SCTE\-35 splice insert \(default\): Select this mode if the input uses splice inserts to indicate ad avails\. The input might also contain messages for others events such as chapters or programs\. 
   + SCTE\-35 time signal apos: Select this mode if the input contains time signals of segmentation type **Placement opportunity**\. The input might also contain messages for other events such as chapters or programs\. 

   The mode identifies which of all possible events are treated as triggers for ad avails and as triggers for blackouts\. In turn, these triggers affect [how manifests are decorated](how-scte-35-events-are-handled-in-manifests.md), [when video is blanked](triggers-for-ad-avail-blanking.md), and [when video is blacked out](triggers-for-blackout.md)\. 

1. In **Ad avail offset**, set a value, if desired\. See the help for this field\.

1. Leave **web\_delivery\_allowed\_flag** and **no\_regional\_blackout\_flag** as Follow for now\. For information about these fields, see [Ad Avail Blanking Restriction Flags](ad-avail-blanking-restriction-flags.md)\. 