# Working with AWS Elemental MediaLive channels<a name="container-channel"></a>

A MediaLive channel ingests and transcodes \(decodes and encodes\) source content from the inputs that are attached to that channel, and packages the new content into outputs\. You create and configure the channel with the details that instruct the channel how to perform this processing\. You then run the channel to start processing\.

Before you start to create a channel, you should [plan your channel](planning-the-channel-in-workflow.md) to identify the following elements:
+ Inputs that the channel will use
+ Output groups for the channel
+ Outputs \(within each output group\)
+ Video, audio, and captions encodes \(in each output\) that the channel will produce

There are three ways to create a channel: 
+ Create from scratch\. 
+ Use a built\-in or custom template\. 
+ Clone an existing channel\. 

Once you have created the channel, you edit or delete it in the same way, regardless of which method you used to create it\.

**Topics**
+ [Creating a channel from scratch](creating-channel-scratch.md)
+ [Creating a channel from a template or by cloning](creating-channel-template-clone.md)
+ [Editing and deleting a channel](editing-deleting-channel.md)
+ [Update the channel class—pipeline redundancy](edit-channel-class.md)
+ [Viewing a channel configuration](viewing-channel-configuration.md)