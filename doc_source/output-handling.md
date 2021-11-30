# Configuring color space handling in each output<a name="output-handling"></a>

For each output, decide how you want to handle the color space and the color space metadata\. You can do the following:
+ Convert the color space in the content to a different color space in the output\. MediaLive supports the following conversions:
  + Convert all content to 601 or 709\. MediaLive also converts the metadata\.
  + Convert all content to HDR10\. This option is available only if the output codec is H\.265 \(HEVC\)\.
+ Remove the color space metadata\. MediaLive doesn't touch the color space itself\.
+ Pass the color space metadata through to the output\. MediaLive doesn't touch the color space itself\.

**Note**  
MediaLive converts from one color space to another based on the metadata in the content\. MediaLive doesn't examine the video to try to determine whether it actually matches the color space identified in the metadata\. Therefore, to successfully convert, the metadata must be as accurate as possible\. To correct the metadata, see [Configuring the handling in the input](input-handling.md)\.

**Topics**
+ [The procedure for output handling](colorspace-output-procedure.md)
+ [Removing color space metadata](colorspace-output-remove.md)
+ [Passing through color space](colorspace-output-passthrough.md)
+ [Converting color space to SDR](colorspace-output-sdr.md)
+ [Converting color space to HDR10](colorspace-output-hdr10.md)