# ABR Asset with Captions Embedded in the Video<a name="an-abr-asset-with-captions-embedded-in-the-video"></a>

For an ABR asset, you create the following outputs and encodes:
+ Several video outputs, each containing one video encode \(for example, one high\-bitrate video, one medium\-bitrate video, and one low\-bitrate video\) and the same embedded captions encode\.
+ One or more audio encodes \(for example, one for each language\)\.

The following illustration shows an example configuration\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-ABR-embed-OPG.png)

Running this channel produces five sets of segmented media files, one set for each video output and each audio output\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-ABR-embed-mediafiles.png)

In outputs that have manifests, it also produces one master manifest and five variant manifests\.