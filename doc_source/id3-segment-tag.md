# Working with ID3 segment tags<a name="id3-segment-tag"></a>

You can include ID3 tags in every segment in the HLS outputs and MediaPackage outputs in an AWS Elemental MediaLive channel\. Typically, you include ID3 segment tags in an output if you know that a downstream system expects the data and can interpret it\.

You should obtain the requirements for the contents of the tag from a representative of the downstream system\.

**How the feature works**

For an HLS output group, you set up individual HLS output groups in a channel so that ID3 segment tagging is enabled for all the outputs in the output group\. For a MediaPackage output group, there is no setup\. Tagging is always enabled in these output groups\.

You then create an ID3 tag action in the channel schedule and specify the contents of the tag\. At the start time for the action, the channel starts inserting the tag content in every segment in the HLS and MediaPackage outputs\. The tag is an ID3 frame of type TXXX\. 

You can change the contents of the tag, by creating a new action\. At the start time of the new action, MediaLive starts inserting the contents of the new tag in every segment\.

**Comparison to ID3 metadata**

A feature that is similar to ID3 segment tagging is [ID3 timed metadata](id3-metadata.md)\. You can set up the channel to include both sets of metadata\. Both sets are inserted in the same PID, but as different types of ID3 metadata\.

Here is a comparison of the two features:


| Topic | ID3 Segment Tags | ID3 Timed Metadata | 
| --- | --- | --- | 
| One time or repeat? | At the start time of the action, MediaLive starts inserting ID3 tags in every segment in the applicable outputs\. It continues to insert in every segment, typically for the life of the channel\. |  At the start time of the action, MediaLive inserts one the ID3 metadata in the applicable outputs, as a one\-time event\.  | 
| Applicable outputs | The applicable outputs are the outputs in the HLS output groups where you have enabled ID3 segment tagging\. | The applicable outputs are the outputs in the HLS output groups where you have enabled ID3 metadata\. | 
| Clear text or blob? |  The tag contents is a string of data in clear text\.   |  The metadata consists of a base64 blob\.   | 
| Typical contents |  Typically, the content consists in all or part of variable text in the form of MediaLive [variable data](variable-data-identifiers.md)\. For example, it might consist of the date and time, and the current segment number, meaning that the tag contents are different in each segment\.  |  You are responsible for creating the base64 blob\. MediaLive doesn't process the contents in any way\. Therefore, the metadata can't contain variable data\.  | 

**Topics**
+ [Inserting ID3 segment tags](id3-segment-enable.md)