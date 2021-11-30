# Input settings—Video selector<a name="input-video-selector"></a>

This section lets you identify the video to extract from the input, and lets you enable the optional color space feature\. 

**To identify the video and color space**

1. In **Video selector**, choose **Video selector**\. More fields appear\. 

1. Complete **Selector settings** as specified in the table after this procedure\. 

   Keep in mind that there is no button to add more video selectors because you can extract only one video asset from the input\.

1. \(Optional\) Complete **Color space** and **Color space usage**\. These fields let you configure the optional color space feature\. For more information, see [Color space handling in AWS Elemental MediaLive](color-space.md)\.

**Determining whether you need to create a video selector**  
When you planned the channel, you should have [identified the video](channel-map-output-source.md) that you need to extract from this input\. 

You must now determine if you need to create a *video selector*, to identify the specific asset to extract from the input\. Some input types require selectors, some input types don't require them\.

The following table specifies whether you need to create a video selector\. 


| Input type | Method of extracting video | 
| --- | --- | 
| CDI | Don't complete Selector settings\. MediaLive extracts the first video that it encounters in the source content\. | 
| Elemental Link | The input contains only one video asset\. MediaLive extracts that video\. There is no need to complete Selector settings\. | 
| HLS |  Don't complete **Selector settings**\. These extraction methods don't apply to HLS inputs\. By default, MediaLive extracts the video asset with the highest bandwidth\. You can complete the **Bandwidth** field \(in **Input settings** – **Network input settings**\)\. MediaLive extracts the highest bandwidth video that is below this limit\.  | 
| MediaConnect | If the input contains an MPTS, choose Selector settings , and enter the program or PID to extract\. If you don't specify the program or PID, MediaLive extracts the first video it finds\.If the input contains an SPTS, MediaLive extracts that video\. There is no need to complete **Selector settings**\. | 
| MP4 | The input contains only one video asset\. MediaLive extracts that video\. There is no need to complete Selector settings\. | 
| RTMP | The input contains only one video asset\. MediaLive extracts that video\. There is no need to complete Selector settings\. | 
| RTP | If the input contains an MPTS, choose Selector settings and enter the program or PID to extract\. If you don't specify the program or PID, MediaLive extracts the first video it finds\.If the input contains an SPTS, MediaLive extracts that video\. There is no need to complete **Selector settings**\. | 