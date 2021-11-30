# General information<a name="eml-metrics-gen-info"></a>

## Collection method<a name="eml-metrics-collection-method"></a>

AWS Elemental MediaLive collects raw data at a specified interval \(typically every second\)\. After a 10\-second window, MediaLive transforms the collected data \(for example, it adds the data or averages the data\), and reports one datapoint for that window\.

## Dimensions for MediaLive<a name="eml-metrics-dimensions"></a>

Each MediaLive metric includes one or two specific sets of dimensions\. MediaLive metrics include the following dimensions, from the dimension with the widest scope to the dimension with the narrowest scope\.
+ ChannelID – Identifies a specific channel\.
+ Pipeline – Identifies a specific pipeline\. Standard channels have two pipelines \(pipeline 0 or pipeline 1\)\. Single\-pipeline channels only have pipeline 0\.
+ ActiveInputFailoverLabel – This dimension identifies the currently active input in a failover pair \(part of the[ automatic input failover feature](automatic-input-failover.md)\)\. Choose a dimension set that includes this dimension only if your channel implements automatic input failover\.

  If you use this dimension, then the metric shows data only for the active input in the channel\. If you don't use this dimension, the metric shows data for both inputs\.
+ OutputGroupName – Identifies a specific output group\.
+ AudioDescriptionName – Identifies a specific audio description \(audio encode\) among all the outputs of a channel\.

## Definition of a running channel<a name="eml-metrics-running-channel"></a>

Many metrics collect data only when a channel is running\.

*Running *means that the channel has started\. It could be both ingesting and producing output\. Or it could be paused, meaning that it is still ingesting but not producing output\.

## Multiple instances of a metric<a name="eml-metrics-multiple-instances"></a>

You can set up a dashboard on CloudWatch with multiples instances of one metric\. For example, one instance that shows a short period, and one that shows a long period\. 