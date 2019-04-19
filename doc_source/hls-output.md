# HLS Output<a name="hls-output"></a>

HLS output supports both passthrough of the SCTE\-35 messages and manifest decoration\. With HLS outputs, passthrough and manifest decoration are either both enabled or both disabled\.

The following table shows the valid processing options\.


****  

| SCTE\-35 Passthrough | Manifest Decoration | Blanking and Blackout | Effect | 
| --- | --- | --- | --- | 
| Enabled | Enabled | Yes or No | Turns on passthrough of SCTE\-35 messages and manifest decoration\. You could also implement blanking and blackout\. | 
| Disabled | Disabled | No |  Turns off passthrough, to remove SCTE\-35 messages from the video stream\. Turns off manifest decoration\. Do not implement blanking or blackout\.  Choose this option only if, in a downstream system, you don't want to replace video that was originally marked by cues\.   | 

Note that with HLS you must either enable passthrough and decoration in all outputs in the same output group, or disable them in all outputs in the same output group\.