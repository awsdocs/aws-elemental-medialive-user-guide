# Channel class and input class<a name="class-channel-input"></a>

One of the characteristics of a channel is its class\. One of the characteristics of an input is its class\. You set both the channel class and input class to implement or to omit pipeline redundancy\.

Read this section for an overview of channel class and input class\. Then for detailed information about implementing or omitting pipeline redundancy, see [Implementing pipeline redundancy](plan-redundancy-mode.md)\.

## About channel classes<a name="about-channel-class"></a>

When you [plan the workflow](plan-redundancy.md), you must decide on the class for the channel\. There are two channel classes:
+ Standard class

  A *standard channel *has two encoding pipelines\. When there are two pipelines, both pipelines perform the encoding\. If one pipeline fails, output to the downstream system can continue, from the other pipeline\. For more information and diagrams about exactly how MediaLive handles the failure, see [Implementing pipeline redundancy](plan-redundancy-mode.md)\.
+ Single\-pipeline class

  A *single\-pipeline channel* has one encoding pipeline\. If the single pipeline fails, output to the downstream system stops\.

You set the channel class when you [create the channel](creating-a-channel-step1.md)\. You can [upgrade or downgrade](pipeline-redundancy-change.md) the class of an existing channel\. 

## About input classes<a name="pipeline-redundancy-input-class"></a>

As part of the steps for implementing or omitting pipeline redundancy in the channel, you must decide on the class for each input\. There are two input classes:
+ Standard class

  A standard\-class input has two pipelines\.

  All types of inputs can be set up as standard\-class inputs\.
+ A single\-class input has one pipeline\.

  Not all inputs can be set up as single\-class inputs\. CDI inputs and RTP inputs can't be set up as single\-class inputs\. 

## Combinations of channel and input class<a name="combinations-channel-input-class"></a>

The following table summarizes the valid combinations of channel class and input class\. The section [Implementing pipeline redundancy](plan-redundancy-mode.md) provides information about choosing the appropriate combination for your workflow\. 


| Channel | Inputs | 
| --- | --- | 
| Standard channel | All inputs must be standard\-class inputs\. | 
| Single\-pipeline channel | The inputs might be a combination of single\-class inputs and standard\-class inputs\.Most types of inputs will be single\-class inputs\.Any CDI inputs or RTP inputs will be standard\-class inputs\. | 
| Single\-pipeline channel | The inputs might all be standard\-class inputs\.  | 