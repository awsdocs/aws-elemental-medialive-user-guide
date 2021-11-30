# The procedure for output handling<a name="colorspace-output-procedure"></a>

Follow this procedure to configure color space handling in each output\. You can set up each output with different color space handling\. For example, you can create one output that passes through the original color space, and another that converts it\.

**To get ready**  
You must decide if you need to enable enhanced VQ mode in the output\. This mode applies only to outputs that use H\.264\. Follow these guidelines:


| Planned conversion | Details | Action | 
| --- | --- | --- | 
|  Convert to SDR  |  You want to convert HDR content as well as SDR content\. For example, you want to convert both 601 and HLG content to 709\.  |  You must enable enhanced VQ mode\.  | 
| Convert to SDR | You don't want to convert any of the HDR content\.For example, you want to convert 709 to 601\. | You don't need to enable enhanced VQ mode\. | 
| Any action | There is no HDR10 or HLG in any of the inputs\. | You don't need to enable enhanced VQ mode\. | 
| Any action | You have already enabled enhanced VQ to improve the video quality\. | Leave the mode enabled\. | 

To enable enhanced VQ mode, see [Setting up enhanced VQ mode](video-enhancedvq.md)\.

**To set up each output**
**Note**  
This section assumes that you are familiar with creating or editing a channel, as described in [Creating a channel from scratch](creating-channel-scratch.md)\. 

1. On the **Create channel **page, in the **Output groups **section, choose the output\.

1. Display the **Stream settings **section, and choose the **Video **section\.

1. Complete the **Width** and **Height** fields to specify a valid resolution\. Make a note of whether you are specifying an SD, an HD, or a UHD resolution\.

1. For **Codec settings**, choose **H264** \(AVC\) or **H265** \(HEVC\)\. 

1. If the resolution is an SD resolution, choose **Codec details**, and then complete the **Profile**, **Tier** \(for H\.265 only\), and **Level** fields\. 

1. If the resolution is an HD or UHD resolution, choose **Codec details**, and then complete **Profile**:
   + If you want to convert the content to an HDR color space, or if you want to pass through an HDR color space, choose one of the profiles that has **10BIT** in the name\.
   + If you want to convert the content to an SDR color space, or if you want to pass through an SDR color space, you can choose any profile\.

1. For **Color space**, choose **Color space settings**, and then choose the appropriate option to remove, pass through, or convert the color space metadata\. For information about the options, see the tables in the following sections\.

1. If you are converting to HDR10, you can optionally complete **Max CLL** and **Max FALL** to set display metadata\. For details about a field on the MediaLive console, choose the **Info** link next to the field\.