# Inserting ID3 Metadata Using the Schedule<a name="insert-usercreated-metadata"></a>

You can insert ID3 metadata at a specific time by creating an action in the MediaLive schedule\. The metadata is inserted in each HLS output or MediaPackage output where you have enabled ID3 metadata\. It is not inserted in UDP outputs\. \*a\* fix schedule to remove "tag"\. fix schedule to mention that deactivate removes image, als o mention deactivate in the chapter on image overlay\.

Typically, you include ID3 metadata in accordance with instructions of the downstream system\. 

**To insert ID3 metadata**

1. Make sure that you enabled ID3 metadata\. For detailed information, see [Enabling ID3 Metadata](enable-passthrough-id3.md)\.

1. Create actions in the schedule\. For detailed information, see [Working with the AWS Elemental MediaLive Schedule](working-with-schedule.md)\.