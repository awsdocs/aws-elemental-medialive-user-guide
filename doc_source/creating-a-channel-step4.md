# Step 5: Create Output Groups<a name="creating-a-channel-step4"></a>

In this step, you create the output groups that you identified when you [planned the channel](planning-workflow.md)\. AWS Elemental MediaLive supports different output types\. For more information, see [Supported Codecs for Outputs](outputs-supported-containers-and-codecs.md)\.

**Important**  
Typically, you set up the MediaLive channel as a [standard channel](channel-class.md)\. The procedures in this chapter assume that you have set up in this way\. The procedures therefore refer to setting up an output group with two destinations\.  
If you will set up the channel as a single\-pipeline channel, then your upstream system has only one source\. The output group has only one destination\.

**Topics**
+ [Creating an Archive Output Group](creating-archive-output-group.md)
+ [Creating a Frame Capture Output Group](creating-framecapture-output-group.md)
+ [Creating an HLS Output Group](creating-hls-output-group.md)
+ [Creating a MediaPackage Output Group](creating-mediapackage-output-group.md)
+ [Creating an RTMP Output Group](creating-rtmp-output-group.md)
+ [Creating a Microsoft Smooth Output Group](creating-smooth-output-group.md)
+ [Creating a UDP Output Group](creating-udp-output-group.md)