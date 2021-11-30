# Inserting ID3 segment tags<a name="id3-segment-enable"></a>

To include ID3 segment tags in the outputs in an output group, enable ID3 segment tagging when you create or edit the channel\. You don't need to enable the feature in MediaPackage output groups\.

Then to set up the channel to start inserting the tag, create an action in the MediaLive schedule\. The channel inserts the tag in the applicable HLS output groups and in every MediaPackage output group\.

**To enable ID3 segment tagging in HLS outputs**

1. On the **Create channel** page, in the **Output groups** section, in the **HLS** group, choose **ID3**\. 

1. For **HLS ID3 Segment Tagging**, choose **ENABLED**\.

1. Optionally, in each output, specify the PID for the tags\. If you don't specify a PID in an output, MediaLive uses PID 502\.

   Choose the output in this output group\. For **Container Settings**, for **PID Settings**, for **Timed Metadata PIDs**, enter the PID where you want to insert the ID3 tag\. 

   Note that the ID3 timed metadata feature also uses this PID\.

1. Repeat for each applicable output in the output group\.

**To enable ID3 segment tagging in MediaPackage outputs**

## <a name="enable-passthrough-mediapackage"></a>

MediaPackage output groups are automatically set up with ID3 segment tagging enabled, and with PID 502 specified\. 

Therefore, if you create an action in the schedule to insert tags, the MediaPackage outputs include that tag\. If you don't create an action, the outputs don't include tags\. \(MediaLive doesn't insert a default tag\.\)

**To start inserting ID3 segment tags**

1. Make sure that you have enabled ID3 segment tags in the HLS output group\. 

1. Create an action in the schedule\. For detailed information, see [Working with the AWS Elemental MediaLive schedule](working-with-schedule.md)\.

   Typically, you create only one action in the schedule\. If you create another action, the tag specified in that action replaces the tag specified in the previous action\.

   To stop MediaLive inserting the tag, create an action with empty content\.