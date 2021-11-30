# Implementing pipeline redundancy<a name="plan-redundancy-mode"></a>

You can set up a channel with two encoding pipelines, to provide resiliency within the channel processing pipeline\. 

When you set up the channel with two encoding pipelines, both pipelines ingest the source content and produce output\. If the current pipeline fails, the downstream system can detect that it is no longer receiving content and can switch to the other output\. There is no disruption to the downstream system\. MediaLive restarts the second pipeline within a few minutes\. 

A channel that has two encoding pipelines is called a *standard channel*\.

If you don't want to implement pipeline redundancy, you set up the channel as a *single\-pipeline channel*\. If the single pipeline fails, MediaLive stops producing output to deliver to the downstream system\.

**Topics**
+ [Deciding whether to implement pipeline redundancy](pipeline-redundancy-guidelines.md)
+ [Setting up a standard channel](standard-channel-procedure.md)
+ [Setting up a single\-pipeline channel with upgrade options](single-channel-upgrade.md)
+ [Setting up a single\-pipeline channel without upgrade potential](single-pipeline-no-upgrade.md)
+ [Changing pipeline redundancy in an existing channel](pipeline-redundancy-change.md)