# Automatic input failover in a standard channel<a name="aif-standard-pipeline-how"></a>

You can implement automatic input failover in a single\-pipeline channel to protect the channel from failure in the upstream system or the network connection that is upstream of MediaLive\. 

You can implement automatic input failover in push inputs, but not in pull inputs\. 

Keep in mind that the channel can't have more than two push inputs\. This means that you can implement one of these scenarios:
+ You can set up two push inputs in the channel, but you won't be able to implement automatic input failover for either of these inputs\.
+ You can set up one push input in the channel, and you can implement automatic input failover for that one input\.

## Setup<a name="aif-standard-setup"></a>

As this diagram illustrates, there are two instances of the content source\. You must make sure that these two instances come from different locations in the upstream system, to provide the desired resiliency in case of a problem upstream of the channel\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/aif-standard-setup.png)

When you start the channel, MediaLive ingests the content from both inputs\. So it ingests four sources\. But only the content from the first input goes to the channel pipeline\. The content from the blue pipeline goes to pipeline 0\. The content from the green pipeline goes to pipeline 1\. 

The pipeline produces two outputs for the downstream system, in the usual way\. The downstream system chooses to handle one pipeline and to ignore the other pipeline\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/aif-standard-beforefailure.png)

## Failure handling<a name="aif-standard-failure-handling"></a>

Failure scenario 1 – If normal processing is in progress and there is a failure in pipeline 0, then the recovery behavior for pipeline redundancy occurs:
+ The downstream system simply switches over to the other pipeline\. For example, it switches from handling pipeline 0 to handling the pipeline 1\.
+ The downstream system must be able to detect the failure in pipeline 0 and switch over to pipeline 1\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/aif-standard-pipeline-failure.png)

Failure scenario 2 – If normal processing is in progress and there is a failure upstream of the first input, then automatic input failover occurs:
+ The channel immediately fails over to the second input \(which is already being ingested\) and starts processing that input\. The yellow line is processed in pipeline 0, the pink line in pipeline 1\. The output is not affected\. 
+ The downstream system continues to handle the output from the pipeline it had chosen before the problem\. The downstream system is not affected by the failure in the first input\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/aif-standard-input-failure.png)