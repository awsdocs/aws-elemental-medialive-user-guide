# Microsoft Smooth Output<a name="ms-smooth-output"></a>

Microsoft Smooth output does not support passthrough of the SCTE\-35 messages, but does support instructions in the sparse track\. The following table shows the valid processing options\.


****  

| SCTE\-35 Passthrough | Manifest Decoration | Blanking and Blackout | Effect | 
| --- | --- | --- | --- | 
| Not applicable \(SCTE\-35 messages are never included in output\) | Enabled | Yes or No | SCTE\-35 messages are removed from the video stream\. But instructions are included in the sparse track\. You could also implement blanking and blackout\. | 
| Not applicable | Disabled | No | SCTE\-35 messages are removed from the output\. The sparse track doesn't include instructions\. Don't implement blanking or blackout because without SCTE\-35 messages in the video stream and without data in the sparse track, it will be impossible to find these blanks and blackouts programmatically in the output\. | 