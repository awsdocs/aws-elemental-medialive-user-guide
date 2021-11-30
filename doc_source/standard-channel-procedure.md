# Setting up a standard channel<a name="standard-channel-procedure"></a>

If you want to implement pipeline redundancy with a new channel, make sure that you set up the inputs as standard\-class inputs and set up the channel as a standard channel\. 

Follow these guidelines when you plan the workflow:
+ Make sure that the upstream system can provide you with two instances of the source content\. See [Assess source formats and packaging](uss-obtain-info.md)\.
+ When you get to the step to[create inputs](step-setting-up-upstream.md), set up all the inputs as standard\-class inputs\.

  Some inputs — CDI inputs and RTP inputs — are always set up as standard\-class inputs\. For all other inputs, set the **Input class** field to **Standard input**\.
+ After you have created the inputs and you are at the step where you [coordinate with the upstream system](step-setting-up-upstream.md) about how they will provide the content, make sure that they provide two content sources\.
+ When you get to the step to create the channel, do the following:
  + Set up the channel as a standard channel\. See [Step 1: Complete the channel details](creating-a-channel-step1.md)\.
  + At the step to [attach inputs to the channel](creating-a-channel-step2.md), attach only standard\-class inputs\. If you try to attach a single\-class input to a standard channel, you won't be able to create the channel\.

## How pipeline redundancy works<a name="standard-pipeline-diagram"></a>

When you set up a standard channel, the channel has two pipelines—pipeline 0 and pipeline 1\. Each input also contains two pipelines\. A content source is connected to each pipeline\.

As this diagram illustrates, the upstream system provides two instances of the content to the input\. One instance goes to the pipeline that is indicated by the blue line, the other goes to the pipeline indicated by the green line\. Each of these lines is attached to one of the two pipelines in the channel\. The channel produces two identical instances of the output for the downstream system\. The downstream system chooses to handle one instance \(the output from blue pipeline\) and to ignore the other instance \(the output from the green pipeline\)\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/pipeline-redundancy-standard-channel.png)

## Failure handling<a name="standard-pipeline-failure-handling"></a>

There might be a problem that causes a pipeline to stop functioning\. 
+ If the failed pipeline is the pipeline that the downstream system is handling \(for example, the blue pipeline\), the downstream system can switch to the other output\.
+ After a few minutes, the failed pipeline automatically restarts and produces output\. The downstream system can continue to handle the output from the green pipeline, or it can go back to the blue pipeline\. That decision has no impact on MediaLive\.

In this diagram, notice that the upstream system is still sending source content to the blue pipeline, which indicates that the upstream system is working but pipeline 0 has failed\. The downstream system has started handling pipeline 1 instead, using the source content from the green pipeline\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/pipeline-redundancy-standard-failure.png)