# Customizing the paths inside HLS manifests<a name="hls-manifest-paths"></a>

This section applies only to HLS outputs\. Inside the HLS main manifest, there are paths to each child manifest\. Inside each child manifest, there are paths to the media files for that manifest\. 

You can optionally change the syntax of these paths\. Typically, you only need to change the syntax if the downstream system has special path requirements\. Akamai CDNs usually require you to change the syntax\.

Don't set up custom paths if the downstream system is MediaPackage\. MediaPackage works with the default paths\.

**Note**  
The information in this section on HLS manifests assumes that you are familiar with the general steps for creating a channel, as described in [Creating a channel from scratch](creating-channel-scratch.md)\.  
The key fields in the console that relate to this feature are in the **Location** grouping of the **HLS output group** section on the **Create channel** page\. To review the step where you complete these fields, see [Procedure to create an HLS output group](hls-create-procedure.md)\.

**Topics**
+ [Procedure to set up custom paths](hls-custom-manifests-procedure.md)
+ [How manifests work](hls-manifests-how-work.md)
+ [Rules for custom paths](hls-custom-paths-rules.md)
+ [Guidance for setting up for custom paths](hls-custom-paths-guidance.md)
+ [Examples of custom paths](hls-custom-paths-examples.md)