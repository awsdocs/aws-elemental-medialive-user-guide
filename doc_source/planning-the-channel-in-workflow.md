# Planning the channel in the MediaLive workflow<a name="planning-the-channel-in-workflow"></a>

You should plan the AWS Elemental MediaLive channel as the second stage of planning a transcoding *workflow*\. You should have already performed the first stage of setting up the [upstream and downstream systems](container-planning-workflow.md)\.

The channel provides the ability to configure for different characteristics of the outputs, and for including a wide array of video features\. But before you plan these details, you should plan the basic features for the channel\.

This chapter describes how to plan these basic features\. If you take the time to carefully plan these features of the channel, the job of creating the channel will proceed more smoothly\.

**Note**  
On the output side, we refer to each video or audio or caption stream, track, or program as an *encode*\.

**Topics**
+ [Step 1: Identify the output encodes](planning-encodes.md)
+ [Step 2: Map the output encodes to the sources](channel-map-output-source.md)
+ [Step 3: Design the output groups](designing-opgs.md)
+ [Step 4: Design the encodes](designing-encodes.md)
+ [Next steps](plan-channel-next.md)