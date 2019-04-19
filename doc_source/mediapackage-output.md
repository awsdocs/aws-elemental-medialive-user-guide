# MediaPackage Output<a name="mediapackage-output"></a>

MediaPackage output, which is a type of HLS output, supports both passthrough of the SCTE\-35 messages and manifest decoration\. With MediaPackage outputs, passthrough and manifest decoration are always enabled and can't be disabled\.

The following table shows the valid processing option\.


****  

| SCTE\-35 Passthrough | Manifest Decoration | Blanking and Blackout | Effect | 
| --- | --- | --- | --- | 
| Enabled | Enabled | Yes or No | Passthrough of SCTE\-35 messages and manifest decoration are always enabled and can't be disabled\. You could also implement blanking and blackout\. | 