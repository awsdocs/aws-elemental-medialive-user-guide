# Color space handling in AWS Elemental MediaLive<a name="color-space"></a>

The source video might use a specific *color space* and a specific *brightness function*\. The source video might also carry *metadata *that describes aspects of the color\.

You can work with color space in two places in the channel—in the input and in the output\.

**Working with color space on the input side – correcting the metadata**

On the input side, you can choose between two options\. These options relate only to the metadata:
+ You can set up to pass through any metadata to the output\.
+ You can set up to correct the color space metadata and pass that corrected metadata to the output\. 

MediaLive lets you set up each input independently\.

By default, MediaLive passes through \(without correction\) any color space metadata that is present\. It passes through both SDR and HDR metadata\. 

**Working with color space on the output side – changing the color space and the metadata**

On the output side, you can choose between three options\. These options relate to the color space and its metadata:
+ You can set up to pass through the content color space\. MediaLive doesn't touch the color space or metadata\.
+ You can set up to remove the color space metadata\. MediaLive doesn't touch the color space but it removes the metadata\.
+ You can set up to convert the color space that is in the video content to another color space, and change the color space metadata to match that conversion\. MediaLive touches both the color space and the metadata\.

MediaLive lets you set up each output independently\.

By default, MediaLive doesn't convert the color space or change the color space metadata\. It passes through the source color space and metadata to the output\.

**Topics**
+ [Color space versus video resolution](color-space-vs-resolution.md)
+ [General information about color space](about-color-metadata.md)
+ [Configuring the handling in the input](input-handling.md)
+ [Configuring color space handling in each output](output-handling.md)