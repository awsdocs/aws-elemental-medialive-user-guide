# Non\-ABR Asset with Captions Embedded in the Video<a name="a-nonabr-asset-with-captions-embedded-in-the-video"></a>

For a non\-ABR asset, you create the following outputs and encodes in the channel: one output that contains one video asset, as many audio assets as you require, and as many captions assets as you require\.

The following illustration shows one output in one output group\. The output contains one video asset, one captions asset, and two audio assets\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-nonABR-embed-OPG.png)

Running this channel produces one segmented media file that contains the video, captions, and audio encodes\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-nonABR-embed-mediafiles.png)

In outputs that have manifests, it also produces one manifest file and one variant manifest file\. 