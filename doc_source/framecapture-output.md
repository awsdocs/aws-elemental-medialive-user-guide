# Frame Capture Output<a name="framecapture-output"></a>

A frame capture output doesn't support passthrough of the SCTE\-35 messages\. However, if blanking or blackout has been enabled \(at the channel level\), then content that falls between the start and stop of the blackout will be blanked or blacked out, even though no SCTE\-35 messages are present\. The following table shows the valid processing options\.


****  

| SCTE\-35 Passthrough | Manifest Decoration | Blanking and Blackout | Effect | 
| --- | --- | --- | --- | 
| Not applicable \(SCTE\-35 messages are never included in output\) | Not applicable | Yes or No | If you implement blanking or blackout \(in order to enable these features for other outputs in the channel\), then the affected content will be blanked or blacked out in the frame capture\. | 