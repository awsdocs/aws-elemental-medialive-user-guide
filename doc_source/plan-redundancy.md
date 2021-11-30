# Step 3: Identify resiliency requirements<a name="plan-redundancy"></a>

Resiliency is the ability of the channel to continue to work when problems occur\. MediaLive includes two resiliency features that you must plan for now\. You must decide which of these features you want to implement\. You must make this decision now because these features affect how many sources you need for your content, which requires discussion with your upstream system\.

## Pipeline redundancy<a name="decide-resil-pipeline"></a>

You can set up a channel with two pipelines, to provide resiliency within the channel processing pipeline\. 

Pipeline redundancy is a feature that applies to the entire channel and to all the inputs attached to the channel\. Early on in your planning of the channel, you must decide how you want to set up the pipelines\. 

You set up for pipeline redundancy by setting up the channel as a *standard channel* so that it has two encoding pipelines\. Both pipelines ingest the source content and produce output\. If the current pipeline fails, the downstream system can detect that it is no longer receiving content and can switch to the other output\. There is no disruption to the downstream system\. MediaLive restarts the second pipeline within a few minutes\.

For more information on pipeline redundancy, see [Implementing pipeline redundancy](plan-redundancy-mode.md)\.

## Automatic input failover<a name="decide-resil-aif"></a>

You can set up two push inputs for automatic input failover, to provide resiliency for one input in the channel\.

Automatic input failover is a feature that applies to individual inputs\. You don't have to make a decision about implementing automatic input failover when planning the channel\. You can implement it later on, when attaching a new push input, or when you want to upgrade an existing push input so that it implements automatic input failover\. 

To set up for automatic input failover, you set up two push inputs \(that have the exact same source content\) as an *input failover pair*\. Setting up this way provides resiliency in case of a failure in the upstream system, or between the upstream system and the channel\. 

In the input pair, one of the inputs is the *active * input and one is on *standby*\. MediaLive ingests both inputs, in order to always be ready to switch, but it usually discards the standby input immediately\. If the active input fails, MediaLive immediately fails over and starts processing from the standby input, instead of discarding it\.

You can implement automatic input failover in a channel that is set up for pipeline redundancy \(a standard channel\) or one that has no pipeline redundancy \(a single\-pipeline channel\)\. 

For more information about automatic input failover, see [Implementing automatic input failover](automatic-input-failover.md)\.

## Comparison of the two features<a name="resil-compare-features"></a>

Following is a comparison of pipeline redundancy and automatic input failover\.
+ There is a difference in the failure that each feature deals with:

  Pipeline redundancy provides resiliency in case of a failure in the MediaLive encoder pipeline\.

  Automatic input failover provides resiliency in case of a failure ahead of MediaLive, either in the upstream system or in the network connection between the upstream system and the MediaLive input\.
+ Both features require two instances of the content source, so in both cases your upstream system must be able to provide two instances\. 

  With pipeline redundancy, the two sources can originate from the same encoder\. 

  With automatic input failover, the sources must originate from different encoders, otherwise both sources will fail at the same time, and the input failover switch will fail\.
+ Pipeline redundancy applies to the entire channel\. Therefore you should decide whether you want to implement it when you plan the channel\. Automatic input failover applies to only one input\. Therefore you could, for example, decide to implement automatic input failover only when you attach your most important push input\.
+ Automatic input failover requires that the downstream system be able to handle two instances of the output and be able to switch from one \(when it fails\) to the other\. MediaPackage, for example, can handle two instances\.

  If your downstream system doesn't have this logic built in, then you can't implement automatic input failover\.