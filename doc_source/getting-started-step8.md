# Step 10: Start the upstream system and the channel<a name="getting-started-step8"></a>

You can now start the upstream system in order to push the streaming content to MediaLive, encode the content, and send it to AWS Elemental MediaPackage\. You can preview the output on MediaPackage\.

**To start the upstream system**

1. In your upstream system, start streaming the video sources that you set up in [Step 1: Set up the upstream system](getting-started-step1.md)\. Set them up to push to the two destinations that you noted in [Step 3: Create an input](getting-started-step3.md)\. These are two addresses in the input in MediaLive\. For example, **rtp://198\.51\.100\.10:5000** and **rtp://192\.0\.2\.131:5000**\. 

1. On the **Channels** list, choose the channel\.

1. Choose **Start**\. The channel state changes to **Starting**, then to **Running**\.

1. Switch to the web browser tab or window where the AWS Elemental MediaPackage is displayed\. 

1. Choose the channel link \(not the radio button\)\. On the details page, under **Endpoints**, choose **Play**\. A preview window appears\. 

1. Start the video\. The output from AWS Elemental MediaLive starts playing\.