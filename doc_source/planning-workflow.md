# Planning Your Workflow for AWS Elemental MediaLive<a name="planning-workflow"></a>

To use AWS Elemental MediaLive to transcode a video asset, you follow this basic workflow: 

1. Assess the video source to ensure that MediaLive can accept it\. 

1. Decide on the channel class—decide if you want to create a standard channel that supports redundancy or a single\-pipeline channel that doesn't support redundancy\.

1. Set up the upstream system that will provide the video source to MediaLive\.

1. Create an input for your video asset\.

1. Optionally associate the input with an input security group \(required only for certain types of inputs\)\.

1. Create a channel in which you identify the input to transcode and specify how MediaLive should ingest and encode that input\.

1. Start \(run\) your channel\. MediaLive ingests the input, encodes the input \(and any associated audio, captions, and metadata\), and then creates the output\.

1. Send the output to a downstream system—for example, send the output to an origin service or a packager such as AWS Elemental MediaPackage\. 

**Topics**
+ [Assessing the Video Source](planning-upstream.md)
+ [Determining the Channel Class](plan-redundancy-mode.md)
+ [Setting Up the Upstream System](setting-up-upstream.md)
+ [Planning the Channel](planning-the-channel.md)
+ [Examples of Channel Designs](examples-channel-design.md)
+ [Setting Up the Downstream System](setting-up-downstream-system.md)
+ [Next Steps](#steps-after-plan-workflow)

## Next Steps<a name="steps-after-plan-workflow"></a>

Now that you have set up the upstream and downstream systems and have created the inputs that you need, you are ready to create the channel itself\. See [Creating a Channel from Scratch](creating-channel-scratch.md)\.