# The Procedure to Black out<a name="procedure-enable-blackout"></a>

1. In the channel that you are creating, in the navigation pane, choose **General settings**\. 

1. For **Avail configuration**, set **Avail settings**, if you have not already done so: 

   + SCTE\-35 splice insert \(default\): Select this mode if the input uses splice inserts to indicate ad avails\. The input might also contain messages for others events such as chapters or programs\. 

   + SCTE\-35 time signal APOS: Select this mode if the input contains time signals of segmentation type **Placement opportunity**\. The input might also contain messages for other events such as chapters or programs\. 

     The mode identifies which of all possible events are treated as triggers for “ad avails” and as triggers for “blackouts\.” In turn, these triggers affect how manifests are decorated, when video is blanked, and when video is blacked out\. 

1. For **Ad avail offset**, set a value, if desired\. See the help for this field\.

1. For **web\_delivery\_allowed\_flag** and **no\_regional\_blackout\_flag**, choose appropriate values\. For information about these fields, see [[ERROR] BAD/MISSING LINK TEXT](triggers-for-blackout.md)\.

   + **Follow **\(default\): Observe the restriction and blank the content for the ad avail event\.

   + **Ignore**: Ignore the restriction and do *not* blank the content for the ad avail event\.
**Warning**  
Never set both fields to **Ignore**\.

1. In **Blackout slate**, in **State**, choose **Enabled**\.

1. For **Blackout slate image**, choose the appropriate value:

   + **Disable**: To use a plain black image for blackout\.

   + **Avail blanking image**: To use a special image for blackout\. In the **URI** field, enter the path to a file in an Amazon S3 bucket\. The file must be of type \.bmp or \.png\. Also enter the user name and EC2 password key for accessing the S3 bucket\. For information on this key, see [[ERROR] BAD/MISSING LINK TEXT](about-EC2Password.md)\.

1. If you want to enable network end blackout \(in other words, black out content when network transmission has ended and remove blackout only when network transmission resumes\), continue reading\. If you don't want to enable it, you have now finished setting up\. 

1. For **Network end blackout**, choose **Enabled**\.

1. For **Network end blackout image**, choose the appropriate value:

   + **Disable**: To use a plain black image for blackout\.

   + **Network end blackout image**: To use a special image for network end blackout\. In the **URI** field, enter the path to a file in an Amazon S3 bucket\. The file must be of type \.bmp or \.png\. Also enter the user name and EC2 password key for accessing the S3 bucket\. See [[ERROR] BAD/MISSING LINK TEXT](about-EC2Password.md)\.

1. For **Additional settings**, in **Network ID**, type the EIDR ID of the network in the format 10\.nnnn/xxxx\- xxxx\- xxxx\- xxxx\-xxxx\-c \(case insensitive\)\. Only network end events with this ID will trigger blackout\.