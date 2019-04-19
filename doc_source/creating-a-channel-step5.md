# Step 6: Create Outputs<a name="creating-a-channel-step5"></a>

Every output group contains one or more outputs\. Each output contains the individual video, audio, and captions encodes and configuration information for the type of output\. For example, it contains configuration information that is specific to an HLS output\.

This section describes how to create and configure the outputs and assumes that you have [created the output group](creating-a-channel-step4.md)\. 

**To create an output in any output group**

1. On the **Create channel** page, in the **Output groups** section, the **Output** section by default has one output\. If you need to create more outputs \(as determined when you [planned the channel](planning-the-channel.md)\), then choose **Add Output** as many times as required\. A new output line is added\.

1. Choose the **Settings** link beside the first output line\. The content pane shows the fields for that output\. 

   The pane for all output types shows two sections: **Output settings** and **Stream settings**\. 

1. Complete both the **Output settings** and **Stream settings** for the output type: [Settings for an Archive Output](output-settings-archive.md), [Settings for an HLS Output](output-settings-hls.md), [Settings for a Microsoft Smooth Output](output-settings-smooth.md), or [Settings for a UDP Output](output-settings-udp.md)\.

1. When you have finished with the fields for this output, go to the next output in this output group\. After you set up all the outputs in the output group, go to the outputs in the next output group\.

After you set up all outputs, go to the [next step](creating-a-channel-step6.md)\.

**Topics**
+ [Settings for an Archive Output](output-settings-archive.md)
+ [Settings for a Frame Capture Output](output-settings-framecapture.md)
+ [Settings for an HLS Output](output-settings-hls.md)
+ [Settings for a MediaPackage Output](output-settings-emp.md)
+ [Settings for an RTMP Output](output-settings-rtmp.md)
+ [Settings for a Microsoft Smooth Output](output-settings-smooth.md)
+ [Settings for a UDP Output](output-settings-udp.md)