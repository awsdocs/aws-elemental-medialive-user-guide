# Setting up Nielsen watermarks<a name="watermark-procedure"></a>

You can create new Nielsen watermarks on the output audio encoding\. To pass through existing Nielsen watermarks or convert them to ID3, see [Converting Nielsen watermarks to ID3](feature-nielsen-id3.md)\.

**To create Nielsen watermarks**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, select **Channels**\. Select the channel you would like to add the watermarks to\. You can also do this during initial channel creation\. After you have created output audio, proceed from step 4\.

1. In the **Channel Actions** dropdown menu, select **Edit channel**\.

1. In the **Channel** navigation pane, locate the output you want to use in the **Output groups** section\. Select it\.

1. In the **Stream settings** section, select the audio encode you want to use\.

1. Expand the **Additonal settings** menu\.

1. In the **Audio Watermark Settings** drop\-down menu, select **Audio watermark**\.

1. In the **Nielsen Watermark Settings** drop\-down menu, select **Nielsen watermark**\.

1. In **Nielsen Distribution Type**, select **Program content** or **Final distribution** to assign the distribution type to the watermarks\.
   + **Program content** \- Assigned to syndication content or to content providers\. 
   + **Final distributon** \- Assigned to local broadcast affiliates or to cable network content\. 

1. Determine if you need CBET or NAES II/NW encoding, or both\. Use the following steps, based on your needs\. If you are implementing both CBET and NAES II/NW, follow both procedures\. 

**To implement CBET encoding**

1. In the **CBET Settings** drop\-down menu, select **Nielsen CBET**\. This selection will reveal additional CBET settings\.
   + **CBET Source ID \(CSID\)** \- This value will be provided to you by Nielsen\.
   + **CBET Check Digits** \- This value will be provided to you by Nielsen\.
   + **CBET Stepaside** \- If set to Enabled, pre\-existing Nielsen watermarks are left intact\. MediaLive inserts new watermarks only in portions of the audio stream where there are no pre\-existing watermarks\. If set to Disabled, any pre\-existing Nielsen watermarks are overwritten by the newly created ones\. 

1. Continue to configure the channel with your desired settings and choose **Create/Update** to save your changes\.

**For NAES II/NW encoding**

1. In the **NAES II and NW Settings** drop\-down menu, select **Nielsen NAES II and NW**\. This selection will reveal additional NAES II/NW settings\.
   + **Source ID \(SID\)** \- This value will be provided to you by Nielsen\.
   + **Check Digits** \- This value will be provided to you by Nielsen\.

1. Continue to configure the channel with your desired settings and choose **Create/Update** to save your changes\.