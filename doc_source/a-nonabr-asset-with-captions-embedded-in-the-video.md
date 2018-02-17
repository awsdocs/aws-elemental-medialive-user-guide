# Non\-ABR Asset with Captions Embedded in the Video<a name="a-nonabr-asset-with-captions-embedded-in-the-video"></a>

For a non\-ABR asset, you create the following outputs and encodes in the channel:

One output that contains one video, as many audios as you require, and as many captions assets as you require\.

For example:

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-nonABR-embed-OPG.png)

Running this channel produces one segmented media file that will contain the video and audio encodes\. In outputs that have manifests, it will also produce one manifest file and one variant manifest file\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-nonABR-embed-mediafiles.png)