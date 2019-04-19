# Input Settings—Video Selector<a name="input-video-selector"></a>

This section lets you identify the video to extract from the input, and lets you enable the optional color space feature\. 
+ In **Video selector**, choose **Video selector**\. More fields appear\. 
+ **Selector settings**: This field lets you identify the video to ingest\. 

  With RTP input, this field is optional but highly recommended because the input might contain more than one video\. If you don't identify the video, MediaLive selects the first video it finds, which might result in undesired content, especially in a live streaming context\. If you want to explicitly identify the video but you don't know its program ID or PID, speak to the content provider\.

  With all other input types, this field is optional because the input only ever contains one video\.

  You can specify the video by specifying a program ID \(which typically exists in an MPTS input\) or by specifying a PID \(which exists in both MPTS and SPTS inputs\)\.

  Keep in mind that there is no button to add more video selectors because you can extract only one video asset from the input\.
+ **Color space** and **Color space usage**: These fields let you configure the optional color space feature\.