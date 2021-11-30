# UDP output<a name="udp-ts-output"></a>

In a UDP output \(a transport stream\), MediaLive supports SCTE\-35 features as follows:
+ Passthrough of the SCTE\-35 messages – Supported\.
+ Manifest decoration – Not supported because these outputs don't have manifests\.
+ Blanking and blackout – Supported\.

Be careful of setting up so that you have removed messages from the input \(passthrough disabled\) and you have not enabled blanking and blackout\. In this case, the video content that was marked by messages \(in the input\) is not marked \(in the output\)\. 
+ If you have the rights to that video content, there is no problem setting up this way\.
+ If you don't have the rights, then the only way to find that content is to look for the IDR i\-frames that identify where the SCTE\-35 message used to be\.