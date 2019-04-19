# Getting Started with AWS Elemental MediaLive<a name="getting-started"></a>

This tutorial describes how to ingest a video source from an RTP source and generate one HLS output that contains one H\.264 video encode and one audio encode\. MediaLive will send the output to AWS Elemental MediaPackage\. The output will consist of the following: 
+ One master manifest: channel\.m3u8
+ One rendition manifest: channel\_1\.m3u8
+ TS files for each output: channel\_1\.00001\.ts, channel\_1\.00002\.ts, channel\_1\.00003\.ts, and so on

This tutorial uses the default values for most configuration fields in the channel\.

**Note**  
All the text marked as an example in this tutorial is just that—a sample that shows what a piece of information typically looks like\. You must replace each example with the information that is valid for your situation\.

## Prerequisites<a name="getting-started-prerequisites"></a>

Before you can use MediaLive, you need an AWS account and the appropriate permissions to access, create, and view MediaLive components\. Complete the steps in [Setting Up AWS Elemental MediaLive](setting-up.md), and then return to this tutorial\. You can't use MediaLive, even as an administrator with full access, until you perform those steps\.

## Step 1: Set Up the Upstream System<a name="getting-started-step1"></a>

The upstream system is the system that streams the video to MediaLive\. The upstream system can be anything from an on\-premises appliance that is serving as a "contribution encoder" to an application running on a smart phone\. You must perform some setup of your upstream system before you start working with MediaLive\. 

For the purposes of this tutorial, the upstream system must be capable of sending a video stream via RTP push\. 

In a "push" delivery, the upstream system is pushing the stream *from *two IP addresses on the upstream system \(for example, from **203\.0\.113\.111** and from **203\.0\.113\.112**\)\. The upstream system will push *to* two IP addresses on MediaLive \(for example, **rtp://198\.51\.100\.10:5000** and **rtp://192\.0\.2\.131:5000**\)\. In the following steps, you will set up MediaLive so that the two *from* IP addresses are white listed\. Furthermore, MediaLive will generate the two *to* IP addresses\. You will set up the upstream system to push to those addresses\.

**To set up the upstream system**

1. Set up your upstream system to perform an RTP push from two different IP addresses\. You must push from two addresses because MediaLive always expects redundant inputs\.

1. Make a note of the IP addresses\. For example, **203\.0\.113\.111** and from **203\.0\.113\.112**\. You will need these addresses when you set up the input security group in a later step\. 

## Step 2: Set Up the Downstream System<a name="getting-started-step2"></a>

In this tutorial, the downstream system \(the destination for the output from MediaLive\) is AWS Elemental MediaPackage\. 

You must set up a channel in AWS Elemental MediaPackage, and you must set it up now because you need the two input URLs that AWS Elemental MediaPackage generates\. You enter these input URLs into MediaLive\.

**To set up the downstream system**

1. Sign in to the AWS Management Console and open the MediaPackage console at [https://console\.aws\.amazon\.com/mediapackage/](https://console.aws.amazon.com/mediapackage/)\.

1. In a new web browser tab or window, display the [Getting Started for AWS Elemental MediaPackage](https://docs.aws.amazon.com/mediapackage/latest/ug/getting-started.html) and follow steps 1 to 3 to create one channel and its endpoint\.

1. Make a note of the data that AWS Elemental MediaPackage has generated: two input URLs and their associated names and passwords\. For example, the data for one input URL might be:
   + `https://39fuo4.mediapackage.us-east-1.amazonaws.com/in/v1/88dpie/channel`
   + `ue739wuty`
   + `due484u`

   Your channel might be in a different Region from the example\.

1. Keep the web browser open; don't close it yet\.

## Step 3: Create an Input<a name="getting-started-step3"></a>

You must create an input\. The input defines how the upstream system provides the source video stream to MediaLive\. In this tutorial, you create an RTP input\. 

You must also create an input security group for the input\. This input security group applies the rule "only this specific IP address \(an IP address that you own\) can push to this input on MediaLive\." Without the protection of this rule, any third party could push content to an MediaLive input if they know the IP address and port of the input\. 

**To create an input and input security group**

1. Sign in to the AWS Management Console and open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input name**, enter **My RTP push**\.

1. For **Input type**, choose **RTP**\. 

1. In the **Input security group** section, choose **Create**\. 

1. In the text box, enter the IP address that you noted in [Step 1: Set Up the Upstream System](#getting-started-step1) of this tutorial\. Enter the address as a CIDR block\. For example, **203\.0\.113\.111/32** and **203\.0\.113\.112/32**\.

1. Choose **Create input security group**\.

1. Choose **Create** to create the input\.

   MediaLive adds the input to the list of inputs and automatically creates two destinations \(one primary and one redundant\)\. These destinations include the port 5000\. For example,  **rtp://198\.51\.100\.10:5000** and **rtp://192\.0\.2\.131:5000**\. These are the two locations where the upstream system must push the source\. 

1. Make a note of these two addresses because you will need them in [Step 10: Start the Upstream System and the Channel](#getting-started-step8)\.

## Step 4: Set up Key Information<a name="getting-started-step4"></a>

The first step to creating a channel from scratch is to choose the IAM role that MediaLive will use to access the channel when the channel is running \(started\) and specify key characteristics of the input\. Now you are ready to start creating a channel\. The first step is to identify the input\. The channel contains the details that instruct MediaLive how to transcode \(decode and encode\) and package that input into specific outputs\.

The first step to creating a channel from scratch is to choose the IAM role that MediaLive will use to access the channel when the channel is running \(started\) and specify key characteristics of the input\.

**To specify key information for the channel**

1. On the MediaLive console, in the navigation pane, choose **Channels**\.

1. In the **Channels** section, choose **Create channel**\. 

1. In the **Channel and input details** pane, in **General info**, for **Channel name**, enter **Test channel**\.

1. For **IAM role**, choose **Create role from template** and choose **Create IAM role**\. The **Use existing role** list now shows the role **MediaLiveAccessRole**\.

1. Choose **Remember role**\.

## Step 5: Attach the Input<a name="getting-started-step4b"></a>

Now you are ready to identify the input that the channel will ingest\.

**To attach the input to the channel**

1. On the **Create channel** page, in the navigation pane, for **Input attachments**, choose **Add**\.

1. In **Attach input** , for **Input**, **My RTP push** \(the input that you created\.\) 

   The **Attachment name** field is automatically populated with the name of the input itself\. You can leave this name as is\. 

1. Choose **Confirm**\. The **Input attachment** section closes, and the **General input settings** section appears\.

## Step 6: Set up Input Video, Audio, Captions<a name="getting-started-step4a-input-selectors"></a>

You can create "selectors" to identify the specific video, audio, and captions that you want to extract from the input\. 

In this tutorial, you don't create a video selector\. Instead, when the channel starts, MediaLive will automatically select the video \(or the first video\) in the input\. You also don't create a captions selector Typically, you include captions in the channel configuration, but in this tutorial we omit them\.

You do create an audio selector\.

**To identify the content to extract**

1. On the **Create channel** page, in the **Input settings** pane, for **Audio** selectors, choose **Add audio selectors**\.

1. For **Audio selector name**, enter **My audio source**\.

   Ignore the **Selector settings** field\. You don't need to specify the PID or language\. When the channel starts, MediaLive will automatically select the first audio, which is acceptable for this tutorial\.

1. For all other fields in this pane, keep the default values\. 

## Step 7: Create an HLS Output Group<a name="getting-started-step5"></a>

Once you have set up the input, you continue with the channel creation by creating an output group\. In this tutorial, you set up an HLS output group\.

**To create an output group**

1. On the **Create channel** page, in the **Output groups** section, choose **Add**\. 

1. In the **Add output group** section, choose **HLS**, and then choose **Confirm**\. 

1. In the **HLS group destination A** section, for **URL**, enter the first input URL that AWS Elemental MediaPackage created for you in [Step 2: Set Up the Downstream System](#getting-started-step2)\. For example, **https://39fuo4\.mediapackage\.us\-east\-1\.amazonaws\.com/in/v1/88dpie/channel**``\. 

1. For **Credentials**:
   + For **Username**, enter the user name that corresponds to this URL\. For example, **ue739wuty**\. 
   + For **Password**, choose **Create parameter**\. For **Name**, enter **DestinationA\_MyHLS**\. For **Password**, enter the password that corresponds to the URL\. For example, **due484u**\.

1. Choose **Create parameter**\.

   You have created a parameter called **DestinationA\_MyHLS** that holds the password **due484u**\. The parameter is stored in the AWS Systems Manager Parameter Store\. For more information, see [About the Feature for Creating Password Parameters](requirements-for-EC2.md#about-EC2Password)\.

1. For **HLS group destination B**, for **URL**, enter the second input URL that AWS Elemental MediaPackage created for you in [Step 2: Set Up the Downstream System](#getting-started-step2)\. For example, **https://mgu654\.mediapackage\.us\-east\-1\.amazonaws\.com/in/v1/xmm9s/channel**\. 

1. For **Credentials**:
   + For **Username**, enter the user name that corresponds to this URL\. For example, **883hdux**\. 
   + For **Password**, choose **Create parameter**\. For **Name**, enter **DestinationB\_MyHLS**\. For **Password**, enter the password that corresponds to the URL\. For example, **634hjik**\.

1. Choose **Create parameter**\.

   You have created a parameter called **DestinationB\_MyHLS** that holds the password **634hjik**\. The parameter is stored in the AWS Systems Manager Parameter Store\. 

1. In the **HLS settings** section, for **Name**, enter **MyHLS**\. 

1. For **CDN settings**, choose **Hls webdav**\. This is the connection that AWS Elemental MediaPackage \(the downstream system for the channel output\) uses\. 

   Leave the defaults for all the other **CDN settings** fields\.

1. For all other fields in this pane, keep the default values\.

## Step 8: Set Up the Output and Encodes<a name="getting-started-step6"></a>

Now that you have defined one output group in the channel, you can set up an output ins that output group, and specify how you want to encode the video output and the audio output\.

**To set up the output**

1. In the **Output groups** section, choose **Output 1**\. MediaLive automatically added this output when you created the output group\. In addition, MediaLive automatically set up the output with one video and one audio, as shown in the **Stream settings** section\. 

1. In **Stream settings**, choose **Video**\.

1. For **Video description name**, change the default name to **H264 video**\.

1. For **Codec settings**, choose **H264**\.

   Leave the remaining fields with the default values\. Specifically, keep **Width** and **Height** empty to use the same width as the input\.

1. In **Stream settings**, choose **Audio 1**\.

1. For **Audio description name**, change the default name to **AAC audio**\.

1. For **Audio selector name**, enter **My audio source**, which is the audio selector that you created in[Step 6: Set up Input Video, Audio, Captions](#getting-started-step4a-input-selectors)\.

1. For **Codec settings**, choose **AAC**\.

1. Leave the remaining fields with the default values\. 

## Step 9: Create Your Channel<a name="getting-started-step7"></a>

You have entered the minimum required information, so you are ready to create the channel\.

**To create the channel**
+ On the **Create channel** page, under the **Channel** section, choose **Create channel**\. 

  The **Channel** section reappears and shows the newly created channel, named **MyHLS**\. The state changes to **Creating**, then **Ready**\.

## Step 10: Start the Upstream System and the Channel<a name="getting-started-step8"></a>

You can now start the upstream system in order to push the streaming content to MediaLive, encode the content, and send it to AWS Elemental MediaPackage\. You can preview the output on MediaPackage\.

**To start the upstream system**

1. In your upstream system, start streaming the video sources that you set up in [Step 1: Set Up the Upstream System](#getting-started-step1)\. Set them up to push to the two destinations that you noted in [Step 3: Create an Input](#getting-started-step3)\. These are two addresses in the input in MediaLive\. For example,  **rtp://198\.51\.100\.10:5000** and **rtp://192\.0\.2\.131:5000**\. 

1. On the **Channels** list, choose the channel\.

1. Choose **Start**\. The channel state changes to **Starting**, then to **Running**\.

1. Switch to the web browser tab or window where the AWS Elemental MediaPackage is displayed\. 

1. Choose the channel link \(not the radio button\)\. On the details page, under **Endpoints**, choose **Play**\. A preview window appears\. 

1. Start the video\. The output from AWS Elemental MediaLive starts playing\.

## Step 11: Clean Up<a name="getting-started-step9"></a>

To avoid extraneous charges, delete this channel and input when you have finished working with it\.

**To delete the channel**

1. On the **Channels** page, choose the channel\.

1. If needed, choose **Stop**\.

1. Choose **Delete**\.

1. On the **Inputs** page, choose the input\.

1. Choose **Delete**\.