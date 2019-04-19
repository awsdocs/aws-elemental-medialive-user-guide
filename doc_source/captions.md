# Working with Captions<a name="captions"></a>

You can set up the AWS Elemental MediaLive channel to extract captions when it ingests the source, and to include those captions in the output in either the same or a different format\. You can include several captions in the output\. For example, you can include captions for several languages\. You can take a source captions asset and convert it to one format in one output and to another format in a different output\. 

You perform the setup for captions in your AWS Elemental MediaLive channel\. 

By default, AWS Elemental MediaLive does not ingest any captions \(not even captions that are embedded in the video\)\. You must explicitly identify the captions to ingest and the captions to output\.

**Note**  
The information in this captions section assumes that you are familiar with the general steps for creating a channel, as described in [Creating a Channel from Scratch](creating-channel-scratch.md)\. It also assumes that you have started creating a channel, including associating an input with the channel\.

**Topics**
+ [Supported Features](captions-supported-features.md)
+ [Typical Scenarios](typical-scenarios.md)
+ [Setting Up for Captions](setting-up-for-captions.md)
+ [Examples](examples.md)