# Fields for resiliency<a name="hls-resiliency"></a>

The following field relates to implementing resiliency in an HLS output\. 
+ **HLS output group** – **HLS Settings** section – **Input loss action**

Optionally change the value of **Input loss action**\.

**Setting up for most downstream systems**

If you're sending this HLS output to a downstream system other than AWS Elemental MediaPackage, choose the **Info** link to decide which option to choose\. 

**Setting up for MediaPackage**

If you're sending this HLS output to AWS Elemental MediaPackage, set this field to match how you set the [channel class](channel-class.md):
+ If the channel is a standard channel \(to support input redundancy on MediaPackage\), set this field to **PAUSE\_OUTPUT**\. 

  With this setup, if MediaLive stops producing output on one pipeline, MediaPackage detects the lack of content on its current input and switches to the other input\. Content loss is minimized\. 

  \(If you set this field to **EMIT\_OUTPUT**, MediaLive sends filler frames to MediaPackage\. MediaPackage doesn't consider filler frames to be lost content, and therefore doesn't switch to its other input\.\)
+ If the channel is a single\-pipeline channel, set this field to **EMIT\_OUTPUT**\. 

  With this setup, if the pipeline fails in MediaLive then MediaPackage continues delivering to its own downstream system \(although the content will be filler frames\)\. 

  \(If you set this field to **PAUSE\_OUTPUT**, MediaPackage stops updating its endpoint, which might cause problems at the downstream system\.\)