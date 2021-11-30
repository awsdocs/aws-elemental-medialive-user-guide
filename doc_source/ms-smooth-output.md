# Microsoft Smooth output<a name="ms-smooth-output"></a>

In a Microsoft Smooth output, MediaLive supports SCTE\-35 features as follows:
+ Passthrough of the SCTE\-35 messages – Not applicable\. SCTE\-35 messages are never included in this output\. 
+ Manifest decoration – Not supported because these outputs don't have manifests\. However, you can set up to include instructions in the sparse track\.
+ Blanking and blackout – Applicable\. Content in the output is blanked or blacked out if the features are enabled at the channel level\.

Be careful of setting up so that you have the following combination:
+ You have you have not enabled sparse track\.
+ You have not enabled blanking and blackout\. 

In this case, the video content that was marked by messages \(in the input\) is not marked \(in the output\)\. 
+ If you have the rights to that video content, there is no problem setting up this way\.
+ If you don't have the rights, it is impossible to find these blanks and blackouts programmatically in a Microsoft Smooth output\.