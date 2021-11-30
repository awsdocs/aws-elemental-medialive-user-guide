# Setting up a single\-pipeline channel without upgrade potential<a name="single-pipeline-no-upgrade"></a>

If you don't want to implement pipeline redundancy now or in the future, you set up the channel as a single\-pipeline channel, and you set up the inputs as single\-class inputs, where possible\.

**Note**  
Before you decide to implement this option, read the information about [setting up without pipeline redundancy, but with the option to easily upgrade later on](single-channel-upgrade.md)\.

Follow these guidelines when you plan the workflow:
+ When you get to the step to [create inputs](step-setting-up-upstream.md), set up the inputs as follows:
  + Set up CDI inputs and RTP inputs as standard inputs, because that's the only way to set them up\. 
  + Set up all other inputs as single\-class inputs\. To set up the input in this way, set the **Input class** field to **Single input**\.
+ After you have created the inputs and you are at the step where you [coordinate with the upstream system](step-setting-up-upstream.md) about how they will provide the content, make sure that they provide *one* content source\. Even if your channel includes CDI inputs or RTP inputs, the upstream system for those inputs should provide only one source\.
+ When you get to the step to create the channel, do the following:
  + Set up the channel as a single\-pipeline channel\. See [Step 1: Complete the channel details](creating-a-channel-step1.md)\.
  + At the step to [attach inputs to the channel](creating-a-channel-step2.md), attach the inputs that you have identified\. The inputs might be both standard\-class inputs and single\-class inputs\.

## How a single\-pipeline channel works<a name="single-pipeline-no-upgrade-working"></a>

When you set up a single\-pipeline channel without any upgrade provision, the channel is a single\-pipeline channel\. The inputs can be a combination of single\-class inputs and standard\-class inputs\.
+ The channel contains one pipeline—pipeline 0\.
+ Each single\-class input that is attached to the channel contains one pipeline\. The input is connected to one content source\. 

  As this diagram illustrates, the upstream system provides one instance of the source content to the input, to the pipeline that is indicated by the blue line\. The input provides that one instance to the one pipeline in the channel\. The channel produces one instance of the output for the downstream system\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/pipeline-redundancy-single-channel-single-input.png)
+ Each CDI input or RTP input that is attached to the channel contain two pipelines\. However, only one of the pipelines is connected to a content source\. The other input pipeline is inactive\.

  As this diagram illustrates, the upstream system provides one instance of the source content to the input, to the pipeline that is indicated by the blue line\. The input provides that one instance to the one pipeline in the channel\. The channel produces one instance of the output for the downstream system\. The other pipeline in the input \(the green pipeline\) is always inactive\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/pipeline-redundancy-single-channel-standard-input.png)

## Failure handling<a name="single-pipeline-no-upgrade-failure"></a>

If there is a problem that causes a pipeline to stop functioning, MediaLive stops producing output\. The downstream system stops receiving output\.