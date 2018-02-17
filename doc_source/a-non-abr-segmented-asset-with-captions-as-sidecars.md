# Non\-ABR Segmented Asset with Captions as Sidecars<a name="a-non-abr-segmented-asset-with-captions-as-sidecars"></a>

Regardless of the kind of ABR stack that you create, sidecar captions are always in their own output, one captions \(language\) per sidecar\. But for the audio, the rule is that with an ABR stack, each audio encode is in its own output, while for a non\-ABR stack, the audio encodes are in the same output as the video\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-nonABR-sidcar-OPG.png)

Running this channel produces one media file that contain video and audio, and one media file for each captions asset\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-nonABR-sidecar-mediafiles.png)