# Getting started tutorial<a name="getting-started-tutorial"></a>

This tutorial describes how to ingest a video source from an RTP source and generate one HLS output that contains one H\.264 video encode and one audio encode\. MediaLive will send the output to AWS Elemental MediaPackage\. The output will consist of the following: 
+ One parent manifest: channel\.m3u8
+ One rendition manifest: channel\-1\.m3u8
+ TS files for each output: channel\-1\.00001\.ts, channel\-1\.00002\.ts, channel\-1\.00003\.ts, and so on

This tutorial uses the default values for most configuration fields in the channel\.

**Note**  
All the text marked as an example in this tutorial is just that—a sample that shows what a piece of information typically looks like\. You must replace each example with the information that is valid for your situation\.

**Topics**
+ [Prerequisites](getting-started-prerequisites.md)
+ [Step 1: Set up the upstream system](getting-started-step1.md)
+ [Step 2: Set up the downstream system](getting-started-step2.md)
+ [Step 3: Create an input](getting-started-step3.md)
+ [Step 4: Set up key information](getting-started-step4.md)
+ [Step 5: Attach the input](getting-started-step4b.md)
+ [Step 6: Set up input video, audio, captions](getting-started-step4a-input-selectors.md)
+ [Step 7: Create an HLS output group](getting-started-step5.md)
+ [Step 8: Set up the output and encodes](getting-started-step6.md)
+ [Step 9: Create your channel](getting-started-step7.md)
+ [Step 10: Start the upstream system and the channel](getting-started-step8.md)
+ [Step 11: Clean up](getting-started-step9.md)