# Working with Captions<a name="captions"></a>

You can set up AWS Elemental MediaLive to include captions when it ingests the source \(either captions present inside the video source or captions from an external file\) and include those captions in the output in either the same or a different format\. You can include several captions in the output\. For example, you can include captions for several languages\. You can take a source captions asset and convert it to one format in one output and another format in a different output\. 

You perform the setup for captions in your AWS Elemental MediaLive channel\. 

By default, AWS Elemental MediaLive does not ingest any captions \(not even captions that are embedded in the video\); you must explicitly identify the captions to ingest and the captions to output\.

**Note**  
The information in this captions section assumes that you are familiar with the general steps for creating a channel, as described in [[ERROR] BAD/MISSING LINK TEXT](creating-channel-scratch.md)\. It also assumes that you have started creating a channel, including associating an input with the channel\.