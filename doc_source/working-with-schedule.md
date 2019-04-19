# Working with the AWS Elemental MediaLive Schedule<a name="working-with-schedule"></a>

In AWS Elemental MediaLive, you can manipulate the processing of a channel while it is running\. You perform this manipulation by inserting actions into the schedule that is associated with the channel\. 

You can use actions to do the following:
+ Switch the input that the running channel is ingesting\.
+ Insert a static image overlay \(an image layered over the underlying video\) into the running channel\.
+ Insert SCTE\-35 messages into the running channel\.
+ Insert ID3 metadata into the running channel\.
+ Pause one or both of the pipelines in the channel\.

This chapter describes how to set up the schedule with the actions that you want\. Before you get started, we recommend that you do the following: 
+ If you want to switch inputs, read the information about setting up a channel to include multiple inputs, as described in [Input Switching in AWS Elemental MediaLive](scheduled-input-switching.md)\.
+ If you want to activate and deactivate image overlays, set up the images that you will use\. See [Working with Image Overlays](working-with-image-overlay.md)\.
+ If you want to insert SCTE\-35 messages, read the information that explains how MediaLive handles SCTE\-35 messages in transport stream \(TS\) outputs\. See [SCTE\-35 Message Processing](scte-35-message-processing.md)\. 
+ If you want to insert ID3 metadata, read the information about the options for ID3 metadata in MediaLive\. See [Working with ID3 Metadata](id3-metadata.md)\.