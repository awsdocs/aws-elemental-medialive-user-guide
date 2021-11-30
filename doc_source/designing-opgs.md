# Step 3: Design the output groups<a name="designing-opgs"></a>

In the first step of planning the channel, you [identified](planning-encodes.md) the video, audio, and captions encodes to include in each output group\.

You must now *organize* these video, audio, and captions encodes into outputs in each output group\. You must organize these encodes to follow the rules that each type of output group dictates\. 

**Result of this procedure**  
After you have performed this procedure, you will have designs for the following:
+ The organization of the outputs in each output group\.
+ The organization of the video, audio, and captions encodes in each output\. 

You have now planned the *output* side of the channel\. 

**AWS Elemental MediaLive compared to AWS Elemental Live**  
If you are familiar with AWS Elemental Live, note that AWS Elemental Live refers to output *streams*, while MediaLive refers to *encodes*\. Apart from that, the concepts are the same: MediaLive channels combine video, audio, and captions encodes into outputs, and outputs are placed in output groups\. 

**Topics**
+ [Organize encodes in an Archive output group](design-archive-package.md)
+ [Organize encodes in a Frame Capture output group](design-framecapture-package.md)
+ [Organize encodes in an HLS or MediaPackage output group](design-hls-package.md)
+ [Organize encodes in a Microsoft Smooth output group](organize-mss-package.md)
+ [Organize encodes in an RTMP output group](design-rtmp-package.md)
+ [Organize encodes in a UDP output group](design-udp-package.md)
+ [Examples](organize-opg-example.md)