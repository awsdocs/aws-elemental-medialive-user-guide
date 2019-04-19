# UDP Output<a name="udp-ts-output"></a>

UDP output supports passthrough of the SCTE\-35 messages, but it doesn't support creation of a manifest\. The following table shows the valid processing options\.


****  

| SCTE\-35 Passthrough | Manifest Decoration | Blanking and Blackout | Effect | 
| --- | --- | --- | --- | 
| Enabled | Not applicable | Yes or No | Turns on passthrough of SCTE\-35 messages\. You could also implement blanking and blackout\. | 
| Disabled | Not applicable | No |  Turns off passthrough, to remove SCTE\-35 messages from the video stream\. Do not implement blanking or blackout\. Choose this option only if, in a downstream system, you don't want to replace video that was originally marked by cues\.   | 