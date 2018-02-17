# Planning Your Workflow for AWS Elemental MediaLive<a name="planning-workflow"></a>

To use AWS Elemental MediaLive to transcode a video asset, you follow this basic workflow: 

1. You create an input for your video asset\. 

1. Optionally, you associate the input with an input security group \(required only for certain types of inputs\)\.

1. You create a channel in which you identify the input to transcode and specify how AWS Elemental MediaLive should ingest and encode that input\.

1. You start \(run\) your channel, and AWS Elemental MediaLive ingests the input\.

1. AWS Elemental MediaLive encodes the input \(and any associated audio, captions, and metadata\), and then creates the output\. 

1. You send the output to a packaging and origination service such as AWS Elemental MediaPackage\. 


+ [Setting up the Upstream System](planning-upstream.md)
+ [Planning the Input](planning-the-input.md)
+ [Planning the Channel](planning-the-channel.md)
+ [Examples of Channel Designs](examples-channel-design.md)
+ [Setting up the Downstream System](setting-up-downstream-system.md)