# Preparing the upstream and downstream systems in the MediaLive workflow<a name="container-planning-workflow"></a>

From the point of view of AWS Elemental MediaLive, a live streaming workflow that includes MediaLive involves three systems: 
+ An *upstream system* that provides the video content to MediaLive\.
+ MediaLive, which ingests the content and transcodes the content\.
+ A *downstream system* that is the destination for the output that MediaLive produces\.

You should plan that workflow before you start to create the channel\. As the first stage in that planning, you must set up the upstream and downstream systems\. As the second stage, you must plan the channel itself—identify the content to extract from the source content, and plan the outputs to produce\.

This chapter deals with preparing the upstream and downstream sections\. [Planning the channel in the MediaLive workflow](planning-the-channel-in-workflow.md) deals with planning the channel\. 

**Important**  
This procedure describes planning the workflow starting from the output and then working back to the input\. This is the most effective way to plan a workflow\.

**To plan the MediaLive workflow**

1. Identify the output groups that you need to produce, based on the systems that are downstream of MediaLive\. See [Step 1: Identify the output group types for the downstream system](identify-downstream-system.md)\.

1. Identify the requirements for the video and audio encodes that you will include in each output group\. See [Step 2: Identify the encode requirements for the output groups](identify-dss-video-audio.md)\.

1. Decide on the channel class—decide if you want to create a standard channel that supports redundancy or a single\-pipeline channel that doesn't support redundancy\. See [Step 3: Identify resiliency requirements](plan-redundancy.md)\.

1. Assess the source content to make sure it's compatible with MediaLive and with the outputs that you need to create\. For example, make sure that the source content has a video codec that MediaLive supports\. See [Step 4: Assess the upstream system](evaluate-upstream-system.md)\.

   After you have performed these four steps, you know whether MediaLive can handle your transcoding request\.

1. Collect identifiers for the source content\. For example, ask the operator at the upstream system for the identifiers for the different audio languages that you want to extract from the content\. See [Step 5: Collect information about the source content](planning-content-extract.md)\.

1. Arrange for setup with the upstream system so that it can connect to MediaLive\. Also, create the MediaLive input so that MediaLive can connect to the upstream system\. See [Step 6: Coordinate with upstream system and create inputs](step-setting-up-upstream.md)\.

1. Coordinate with the downstream system or systems to provide a destination for the output groups that MediaLive will produce\. See [Step 7: Arrange for delivery to downstream systems](setting-up-downstream-system.md)\.

**Topics**
+ [Step 1: Identify the output group types for the downstream system](identify-downstream-system.md)
+ [Step 2: Identify the encode requirements for the output groups](identify-dss-video-audio.md)
+ [Step 3: Identify resiliency requirements](plan-redundancy.md)
+ [Step 4: Assess the upstream system](evaluate-upstream-system.md)
+ [Step 5: Collect information about the source content](planning-content-extract.md)
+ [Step 6: Coordinate with upstream system and create inputs](step-setting-up-upstream.md)
+ [Step 7: Arrange for delivery to downstream systems](setting-up-downstream-system.md)
+ [Next steps](plan-workflow-next.md)