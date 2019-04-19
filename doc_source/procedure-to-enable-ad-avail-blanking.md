# Enabling Blanking<a name="procedure-to-enable-ad-avail-blanking"></a>

Follow this procedure if you want to enable the ad avail blanking feature\.

**To enable blanking**

1. In the channel that you are creating, in the navigation pane, choose **General settings**\. 

1. In **Avail configuration**, set **Avail settings**, if you have not already done so: 
   + SCTE\-35 splice insert \(default\): Select this mode if the input uses splice inserts to indicate ad avails\. The input might also contain messages for others events such as chapters or programs\. 
   + SCTE\-35 time signal APOS: Select this mode if the input contains time signals of segmentation type **Placement opportunity**\. The input might also contain messages for other events such as chapters or programs\. 

     The mode identifies which of all possible events are treated as triggers for ad avails and as triggers for blackouts\. In turn, these triggers affect [how manifests are decorated](how-scte-35-events-are-handled-in-manifests.md), [when video is blanked](triggers-for-ad-avail-blanking.md), and [when video is blacked out](triggers-for-blackout.md)\. 

1. For **Ad avail offset**, set a value, if desired\. See the help for this field\.

1. In **web\_delivery\_allowed\_flag** and **no\_regional\_blackout\_flag**, choose appropriate values\. For information about these fields, see [Triggers for Ad Avail Blanking](triggers-for-ad-avail-blanking.md)\.
   + Follow \(default\): Observe the restriction and blank the content for the ad avail event\.
   + Ignore: Ignore the restriction and do *not* blank the content for the ad avail event\.
**Warning**  
Never set both fields to Ignore\.

   In **Avail blanking**, in **State**, choose **Enabled**\.

1. In **Avail blanking image**, choose the appropriate value:
   + Disable: To use a plain black image for blanking\.
   + Avail blanking image: To use a special image for blanking\. In the **URL** field, type the path to a file in an S3 bucket\. The file must be of type \.bmp or \.png\. Also enter the user name and Systems Manager password parameter for accessing the S3 bucket\. See [About the Feature for Creating Password Parameters](requirements-for-EC2.md#about-EC2Password)\.