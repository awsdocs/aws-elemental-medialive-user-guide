# Configuring the handling in the input<a name="input-handling"></a>

You should identity the color spaces that are in the video content, and decide whether you want to correct the color space metadata\.

Note that there can be a difference between what the color space is, and what the color space metadata states\. When content is in a specific color space, the content uses a defined range of pixel colors\. The color space metadata states which that range is\. Ideally, the metadata matches the actual color space, so that the metadata specifies *601 *and the color space actually is *601*\. But in practice the metadata might be incorrect, might be missing, or might specify a color space that MediaLive doesn't support\.

**Topics**
+ [The procedure for input handling](color-space-input-procedure.md)
+ [Clean up scenarios for color space metadata](color-space-cleanup-scenarios.md)