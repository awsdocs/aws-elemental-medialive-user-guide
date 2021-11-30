# Procedure to set up custom paths<a name="hls-custom-manifests-procedure"></a>

The following fields relate to the paths inside the manifests:
+ **HLS output group – Location** – the **Base URL manifest** fields
+ **HLS output group – Location** – the **Base URL content** fields

**To configure custom paths in manifests**

1. Speak to the downstream system to find out if custom paths are required\. The main manifests might need custom paths to the child manifests, the child manifests might need custom paths to the media files, or both main and child manifests might need custom paths\. See [How manifests work](hls-manifests-how-work.md)\.

1. Design the paths, paying attention to the [syntax and the rules for constructing the paths](hls-destinations-design-step.md#hls-syntax-http)\.

   See this [guidance for different downstream systems](hls-custom-paths-guidance.md)\.

   See [these examples](hls-custom-paths-examples.md)\.

1. Complete one or both of these fields in the **Location** section of the HLS output group page:
   + **Base URL manifest A** and **Base URL manifest B**\. For a single\-pipeline channel, complete only field A\. For a standard channel, complete field A and field B\.
   + **Base URL content A** and **Base URL content B**\. For a single\-pipeline channel, complete only field A\. For a standard channel, complete field A and field B\.