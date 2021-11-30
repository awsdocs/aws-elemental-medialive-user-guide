# Setting up automatic input failover with MediaConnect inputs<a name="aif-setup-emx"></a>

To use MediaConnect inputs with automatic input failover, you must set up both the inputs and the channels in a specific way\.

**Note**  
The information in this section assumes that you are familiar with the general steps for [creating a MediaConnect input](input-create-push-mediaconnect.md) and [creating a channel](creating-channel-scratch.md)\.

**To plan the inputs for the input failover pair**

1. Identify the flows that you need to create on MediaConnect:
   + If you are setting up automatic input failover in a single\-input channel, you need two flows—one for each input\.
   + If you are setting up automatic input failover in a standard channel, you need four flows—two for each input\.

1. Make sure that all the flows contain exactly identical video, audio, captions, and metadata\.

**To create the flows in MediaConnect in a standard channel**

You must create four flows, two for the primary input, and two for the secondary input\.
+ Follow the procedure in [Creating a MediaConnect push input](input-create-push-mediaconnect.md), with the following notes:

  Make sure that you set up the flows in the correct Availability Zones\. Assume that the two flows for the primary input are A and B, and that the two flows for the secondary input are C and D\. 
  + Flow A must be in Availability Zone X\.
  + Flow B must be in Availability Zone Y\.
  + Flow C must be in Availability Zone X\.
  + Flow D must be in Availability Zone Y\.

  At channel startup, MediaLive sets up the flows as follows:
  + Flow A connects to pipeline 0\.
  + Flow C connects to pipeline 0\.
  + Flow B connects to pipeline 1\.
  + Flow D connects to pipeline 1\.

  As a result of these connections, the active input on pipeline 0 is initially from Availability Zone X\. The active input on pipeline 1 is initially from Availability Zone Y\. If one Availability Zone fails, only one pipeline is affected\. For more information on failure scenarios, see [Failover and failback scenarios](aif-behavior-startup.md#aif-failover-scenarios)\.

**To create the flows in MediaConnect in a single\-pipeline channel**

You must create two flows, one for each input\.
+ Follow the procedure in [Creating a MediaConnect push input](input-create-push-mediaconnect.md), with the following note:

  Make sure that you set up the flows in the same Availability Zones\. The two inputs provide two paths to the single pipeline in the channel\. If one of the flows fails to send content, that input fails and MediaLive switches to the other input\.

**To create the inputs for the input failover pair**

1. Follow the procedure in [Creating a MediaConnect push input](input-create-push-mediaconnect.md) to create one input of the appropriate type\. 
   + In a standard channel, set up the input with two sources\. Attach flows A and B to this input\.
   + In a single\-pipeline channel, set up the input with one flow\. 
   + Give the input a name such as **primary input**\.

1. Create a second input in the same way\. 
   + In a standard channel, set up the input with two sources\. Attach flows C and D to this input\.
   + In a single\-pipeline channel, set up the input with one flow\. 
   + Give the input a name such as **secondary input**\.

**To attach the inputs to the channel**

1. In the **Input attachments** section of the **Create channel** page, follow the usual procedure to attach the primary input\. Ignore the **Automatic input failover settings** for now\.

1. Follow the same procedure to attach the secondary input\.

1. In the **Input attachments** section, in the list of input attachments, choose the first input that you attached\. 

1. In the **Automatic input failover settings** section, choose **Enable automatic input failover settings**\. As soon as you enable this field, this input is labeled as **Primary** in the list of input attachments\.

1. For **Secondary input**, choose the secondary input\. \(When you do this, this input is labeled as **Secondary** in the list of attachments\.\)

1. For **Input preference**, choose the desired option\. This field controls the behavior when MediaLive has switched over to the secondary input and then the primary input becomes healthy again\.
   + **EQUAL\_INPUT\_PREFERENCE** – MediaLive remains on the secondary input\. The primary input continues to be processed, but it is not active\.
   + **PRIMARY\_INPUT\_PREFERENCE** – MediaLive switches back to the primary input\. The primary input becomes the active input\.

1. For **Failover conditions**, enable the conditions that you want MediaLive to use to identify input loss\. The fields include help that describes how the conditions work\.