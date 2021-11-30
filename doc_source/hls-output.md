# HLS output<a name="hls-output"></a>

In an HLS output \(a transport stream\), MediaLive supports SCTE\-35 features as follows:
+ Passthrough of the SCTE\-35 messages – Supported\.
+ Manifest decoration – Supported\.
+ Blanking and blackout – Applicable\. Content in the output is blanked or blacked out if the features are enabled at the channel level\.

MediaLive supports the following combinations of passthrough and manifest decoration:
+ Passthrough enabled, decoration enabled\.
+ Passthrough disabled, decoration enabled\.
+ Passthrough disabled, decoration disabled\. Be careful of setting up with this combination but leaving blanking and blackout disabled\. In this case, the video content that was marked by messages \(in the input\) are not marked \(in the output\)\. In addition, the manifests don't have information for identifying that video content\. 
  + If you have the rights to that video content, there is no problem setting up this way\.
  + If you don't have the rights, the only way to find that content is to look for the IDR i\-frames that identify where the SCTE\-35 message used to be\.