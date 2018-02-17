# UDP Output<a name="udp-ts-output"></a>

UDP output supports passthrough of the SCTE\-35 messages, but it does not support creation of a manifest\. Therefore, the processing options that make sense are shown in the following table\.


****  

| SCTE\-35 Passthrough | Manifest Decoration | Blanking and Blackout | Effect | 
| --- | --- | --- | --- | 
| Enabled | Not applicable | Yes or No | Turn on passthrough of SCTE\-35 messages\. You could also implement blanking and blackout\. | 
| Disabled | Not applicable | No |  Turn off passthrough in order to remove SCTE\-35 messages from the video stream\. Do not implement blanking or blackout\. Choose this option only if, in a downstream system, you do not want to replace video that was originally marked by cues\.   | 