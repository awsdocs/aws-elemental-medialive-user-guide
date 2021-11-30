# Getting ready<a name="creating-a-channel-getready"></a>

We recommend that before you start creating the channel, you [plan the workflow](container-planning-workflow.md) and [plan the channel](planning-the-channel-in-workflow.md)\. In both these planning procedures, you obtain information that you need to create the channel\. 

Here is the information that you need, listed in the order in which your will use it when you create the channel:
+ You need the following information in [Step 1: Complete the channel details](creating-a-channel-step1.md):

  Whether you will implement any resiliency features of MediaLive, and particularly whether you will create a standard channel or a single\-pipeline channel\. You made these decisions in step 3 of [Preparing the upstream and downstream systems in the MediaLive workflow](container-planning-workflow.md)\.
+  You need the following information in [Step 2: Attach inputs to the channel](creating-a-channel-step2.md):

  The names of the input or inputs to use in this channel\. You created the input or inputs as part of step 6 of [Preparing the upstream and downstream systems in the MediaLive workflow](container-planning-workflow.md)\.
+ You need the following information to create the input selectors, as part of the procedure in [Step 3: Complete the settings for each input](creating-a-channel-step2a.md):
  + The assets to extract from each input\. You identified these assets in [Step 2: Map the output encodes to the sources](channel-map-output-source.md), as part of planning the channel\.
+ You need the following information in [Step 5: Create output groups and outputs](creating-a-channel-step4.md):
  + The output groups to create\. You should have identified these output groups in step 1 of [Preparing the upstream and downstream systems in the MediaLive workflow](container-planning-workflow.md)\.
  + The outputs to create\. You should have designed the outputs and encodes \(video, audio,and captions\) when you [planned the channel](planning-the-channel-in-workflow.md)\.
  + Information about the destinations for the outputs of each output group\. You obtained this information in step 7 of [Preparing the upstream and downstream systems in the MediaLive workflow](container-planning-workflow.md)\.
+ You need the following information in the three steps that start with [Step 6: Set up the video encode](creating-a-channel-step6.md):
  + Details about the output encodes \(video, audio, and captions\) to create in each output group\. You made these decisions in [Planning the channel in the MediaLive workflow](planning-the-channel-in-workflow.md)\.