# Examples<a name="organize-opg-example"></a>

[Example of a plan for output encodes](plan-encodes-example.md) shows an example of a workflow that includes three output groups\. The table in this section shows the encodes that you might include in each output group\. 

This section shows the results of organizing the encodes in those output groups\.

## HLS output group<a name="organize-opg-hls-example"></a>

The example of an HLS output group contains three videos, each with a different resolution\. The audio encodes are each in their own output, which means that the output group contains an audio rendition group\. The captions are WebVTT, which is a sidecar style of captions\. Therefore, each captions encode goes in its own output\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-example-hls.png)

## RTMP output group<a name="organize-opg-rtmp-example"></a>

The example of an RTMP output group contains one video, one audio, and one captions encode\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-example-rtmp.png)

## Archive output group<a name="organize-opg-archive-example"></a>

The example of an Archive output group contains one video encode, three audio encodes, and one captions encode\. In an Archive output, the video and audio encodes are always each in their own output\. In this example, the captions are WebVTT, which is a sidecar style of captions\. Therefore, each captions encode goes in its own output\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-example-archive.png)