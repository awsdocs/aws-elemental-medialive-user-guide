# HLS Output<a name="hls-output"></a>

HLS output supports both passthrough of the SCTE\-35 messages and manifest decoration\. In fact, with HLS outputs, passthrough and manifest decoration are either both enabled or both disabled\.

Therefore, the processing options that make sense are shown in the following table\.


****  

| SCTE\-35 Passthrough | Manifest Decoration | Blanking and Blackout | Effect | 
| --- | --- | --- | --- | 
| Enabled | Enabled | Yes or No | Turn on passthrough of SCTE\-35 messages and manifest decoration\. You could also implement blanking and blackout\. | 
| Disabled | Disabled | No |  Turn off passthrough in order to remove SCTE\-35 messages from the video stream\. Turn off manifest decoration\. Do not implement blanking or blackout\.  Choose this option only if, in a downstream system, you do not want to replace video that was originally marked by cues\.   | 