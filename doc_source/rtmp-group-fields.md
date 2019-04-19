# Fields for the RTMP Group<a name="rtmp-group-fields"></a>

You must provide information that applies to all the outputs in the individual RTMP output group\.
+ For **Name**, enter a name for the output group\. For example, **My Video Podcast**\.
+ If you want to connect to the destination over RTMPS, for **Authentication Scheme**, specify the type of scheme\. Typically, choose **Common**\. Choose **Akamai** only if instructed to do so by the people responsible for the downstream system\. If you connect over RTMP, the value in this field is ignored\.
+ In **Additional Settings**, optionally change the **Cache length**, **Restart delay**, and **Cache full behavior**\. These fields relate to reconnecting to the RTMP server\. For more information, see [Reconnection Settings](output-settings-rtmp.md#rtmp-connection-fields)\.
+ In **Additional settings**, for **Caption Data**, complete this field only if at least one of your outputs includes captions with **embedded** as the source captions format and **RTMP CaptionInfo** as the output format\. If there are no captions in any output, the value in this field is ignored\. For details about a field, choose the **Info** link next to the field\. For detailed information about setting up for captions, see [Working with Captions](captions.md)\.
+ The **RTMP outputs** section contains fields that are different for each output\. Setup of the individual outputs is described in [Step 6: Create Outputs](creating-a-channel-step5.md)\.

  If you want more than one output in this output group, choose **Add output**\. An **Output** line is added for each output\. 