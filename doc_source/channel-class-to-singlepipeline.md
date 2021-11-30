# Changing the channel to a single\-pipeline channel<a name="channel-class-to-singlepipeline"></a>

You can change a standard channel to single\-pipeline, to remove one of the pipelines in the channel and to remove pipeline redundancy\.

To change the channel class, the channel must be idle \(not running\)\.

**To change the channel class to a single\-pipeline channel**

1. On the **Channels** page, choose the channel\. \(Don't choose the channel name\.\)

1. On the menu, choose **Actions**, then choose **Other channel actions**, then choose **Update channel class to SINGLE\_PIPELINE**\.

1. In the dialog box, choose **Confirm**\. MediaLive performs the following actions:
   + It removes the second pipeline \(pipeline 1\) in the channel\.
   + It removes the second destination address in each output group\.
   + It *doesn't* remove the second endpoint on the inputs\. The inputs aren't changed in any way\. Instead, when you restart the channel, MediaLive simply ignores the second endpoint\.

   While MediaLive is performing these actions, the channel has a status of **UPDATING**\. When the update is completed, the status changes to **IDLE**\. 

1. You might want to notify the upstream system for each push input that it no longer needs to push input to the second endpoint\. You also might want to notify the downstream system for each output group that it should no longer expect output at its second destination\. 