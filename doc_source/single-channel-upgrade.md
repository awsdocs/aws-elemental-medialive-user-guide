# Setting up a single\-pipeline channel with upgrade options<a name="single-channel-upgrade"></a>

When you first create the channel, you might want to set it up without pipeline redundancy\. But you might want to allow for easy upgrade to pipeline redundancy later\. 

Follow these guidelines when you plan the workflow:
+ When you get to the step to [create inputs](step-setting-up-upstream.md), set up all the inputs as standard\-class inputs\.

  Some inputs — CDI inputs and RTP inputs — are always set up as standard\-class inputs\. For all other inputs, set the **Input class** field to **Standard input**\.
+ After you have created the inputs and you are at the step where you [coordinate with the upstream system](step-setting-up-upstream.md) about how they will provide the content, make sure that they provide *one* content source\.
+ When you get to the step to create the channel, do the following:
  + Set up the channel as a single\-pipeline channel\. See [Step 1: Complete the channel details](creating-a-channel-step1.md)\.
  + At the step to [attach inputs to the channel](creating-a-channel-step2.md), double\-check that the inputs you attach are standard\-class inputs\.

## How a single\-pipeline channel works<a name="single-channel-upgrade-working"></a>

When you set up a single\-pipeline channel with the option to easily upgrade, the channel is a single\-pipeline channel but the inputs are all standard\-class inputs\. 
+ The channel contains one pipeline—pipeline 0\.
+ Each standard\-class input contains two pipelines\. However, only one of the pipelines is connected to a content source\. The other input pipeline is inactive\.

As this diagram illustrates, the upstream system provides one instance of the source content to the input, to the pipeline that is indicated by the blue line\. The input provides that one instance to the one pipeline in the channel\. The channel produces one instance of the output for the downstream system\. The other pipeline in the input \(the green pipeline\) is always inactive\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/pipeline-redundancy-single-channel-standard-input.png)

## Failure handling<a name="single-channel-upgrade-failure"></a>

If there is a problem that causes a pipeline to stop functioning, MediaLive stops producing output\. The downstream system stops receiving output\.