# Pipeline locking metrics<a name="eml-metrics-output-lock"></a>

Pipeline locking metrics relate to the synchronization of MediaLive pipelines\.

**Topics**
+ [Pipelines locked](#eml-metrics-pipelines-locked)

## Pipelines locked<a name="eml-metrics-pipelines-locked"></a>

An indicator of whether the two pipelines are synchronized with each other\. This metric applies only to standard channels and only to HLS, MediaPackage, Microsoft Smooth, and UDP outputs in that channel\. MediaLive uses [pipeline locking](pipeline-lock.md) to ensure that the two pipelines are synchronized with each other\. 

With this metric, you must determine whether the channel you are looking at is a standard channel and has at least one eligible output\. If this scenario applies, then a value of 1 means that all the eligible pairs of pipelines are synchronized\. A value of 0 means that at least one pair of eligible pipelines is not synchronized\.

For any other scenario, the metric is always 0\. For example, if the channel is a standard channel with no eligible outputs\. Or the channel isn’t a standard channel\.

**Details:**
+ Units: Not applicable\.
+ Meaning of zero: False \(the eligible pipelines are not synchronized\), but only if the channel is standard\.
+ Meaning of no datapoints: The channel is not running\. 
+ Supported dimension sets: ChannelId, Pipeline
+ Recommended statistic: Minimum \(Value is 0\)\.