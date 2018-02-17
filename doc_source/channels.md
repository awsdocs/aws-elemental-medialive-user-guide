# Channels<a name="channels"></a>

In AWS Elemental MediaLive a *channel* is attached to an input \(source\)\. A channel contains the details that instruct AWS Elemental MediaLive how to transcode \(decode and encode\) and package that input into specific outputs\. The key components of a channel are an encode, an output, and an output group\. 

## Encodes<a name="encode"></a>

An *encode* is the smallest component on the output side of a channel\. Each encode contains the instructions for one video asset, one audio asset, or one captions asset that will be created by the transcoding process\. Different encodes have different characteristics\. For example, one video encode produced from the input may be high resolution while another is low resolution\. Or one audio encode may use the AAC audio codec while another uses the Dolby Digital audio codec\. 

A channel can contain multiple video, audio and captions encodes\.

In the following illustration, the red circle represents a video output, the blue circle represents an audio output, and the green circle represents a captions output\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/encode.png)

## Outputs<a name="output"></a>

An *output* contains the encodes that belong together\. For example, one output will contain the combination of video, audio, and captions encodes that make sense for one purpose, while another output will contain a different combination\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output.png)

The output holds packaging instructions that apply to all the encodes in that output\. For example, the packaging instructions for a UDP output are different from those for an Archive output\. The encodes inside the outputs may be the same or different\. But the packaging instructions are different\.

## Output Groups<a name="output-group"></a>

An *output group* contains related outputs\. An output group may contain only one output or it may contain several outputs The output group holds details about the destination for all the outputs in that group\.  

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output-group.png)

