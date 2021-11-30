# Redundant HLS manifests<a name="hls-redundant-manifests"></a>

When you create an HLS output group in a standard channel, you can enable redundant manifests\. Redundant manifests allow the downstream system \(that reads the manifests\) to better handle an output failure from MediaLive\.

When the redundant manifest feature is enabled, the main manifest for each pipeline references both its own child manifests and the child manifests for the other pipeline\. The downstream system finds the path to the child manifests for one pipeline\. If there is a problem with that pipeline, then there will be a problem with the child manifests for that pipeline\. The downstream system can then refer back to the main manifest to find the child manifest for the other pipeline\. In this way, the downstream system can always continue with its processing of the manifest and media\.

To successfully implement redundant manifests, you must be sure that the downstream system can handle redundant manifests in the ways that are described in the HLS specification\.

**Note**  
The information in this section on HLS manifests assumes that you are familiar with the general steps for creating a channel, as described in [Creating a channel from scratch](creating-channel-scratch.md)\.   
The key fields in the console that relate to this feature are in the **Manifests and segments** grouping of the **HLS output group** section on the **Create channel** page\. To review the step where you complete these fields, see [Procedure to create an HLS output group](hls-create-procedure.md)\.

**Topics**
+ [Procedure to set up redundant manifests](hls-rm-procedure.md)
+ [The media contents of an HLS manifest](hls-rm-manifests-contents.md)
+ [Rules for most downstream systems](hls-redundant-manif-most-systems.md)
+ [Rules for Akamai CDNs](hls-redundant-manif-akamai.md)
+ [Combining redundant manifests with other features](hls-redundant-manif-combine.md)