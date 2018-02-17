# Getting Started with AWS Elemental MediaLive<a name="getting-started"></a>

This tutorial describes how to ingest a video source from an RTP source and generate one HLS output that contains one H\.264 video encode and one audio encode\. AWS Elemental MediaLive will send the output to AWS Elemental MediaPackage\. The output will consist of the following: 

+ One master manifest: channel\.m3u8

+ One rendition manifest called channel\_1\.m3u8\.

+ TS files for each output: channel\_1\.00001\.ts, channel\_1\.00002\.ts, channel\_1\.00003\.ts, and so on\. 

This tutorial uses the default values for most configuration fields in the channel\.

**Note**  
All the text marked as an example in this tutorial is just that – a sample that shows what a piece of information typically looks like\. You must replace each example with the information that is valid for your situation\.

## Prerequisites<a name="getting-started-prerequisites"></a>

Before you can use AWS Elemental MediaLive, you need an AWS account and the appropriate permissions to access, create and view AWS Elemental MediaLive components\. Complete the steps in [[ERROR] BAD/MISSING LINK TEXT](setting-up.md) and then return to this tutorial\. You will not be able to use AWS Elemental MediaLive, even as an administrator with full access, until you have performed those steps\.

## Step 1: Set up the Upstream System<a name="getting-started-step1"></a>

The upstream system is the system that is streaming the video to AWS Elemental MediaLive\. A contribution encode "on the ground" is a typical upstream system\. You must perform some setup of your upstream system before you start working in AWS Elemental MediaLive\. For the purposes of this tutorial, the upstream system must be capable of sending a video stream via RTP\. 

1. Set up your upstream system to perform an RTP push from a specific IP address\. 

   In a typical deployment of AWS Elemental MediaLive, you provide two sources of the video asset you want to encode\. But for this tutorial, you have only one source that you will duplicate within AWS Elemental MediaLive\. This setup is absolutely not recommended for production usage\.

1. Make a note of the IP address\. For example, 192\.0\.2\.0\. 

1. Keep in mind that the input will need to be ready when you start the associated channel\.

## Step 2: Set up the Downstream System<a name="getting-started-step2"></a>

In this tutorial, the downstream system \(the destination for the output from AWS Elemental MediaLive\) is AWS Elemental MediaPackage\. 

You must set up a channel in this service and you must set it up now because you need the input URLs that AWS Elemental MediaPackage will generate; you enter these input URLs into AWS Elemental MediaLive\. You must create two channels in AWS Elemental MediaPackage because you will create two destinations in AWS Elemental MediaLive\.

1. Go to the AWS Elemental MediaPackage console\.

1. In a new web browser tab or window, display the Getting Started for AWS Elemental MediaPackage  and follow steps 1 to 3 to create one channel and its endpoint\.

1. Make a note of the input URL, name, and password that AWS Elemental MediaPackage generates\. For example:

   + https://39fuo4\.mediapackage\.us\-east\-1\.amazonaws\.com/in/v1/88dpie/channel

   + ue739wuty

   + due484u

   Your channel may be in a different region from the example\.

1. Follow steps 1 to 3 again to create the second channel and its endpoint\.

1. Make a note of the input URL, name, and password\. For example:

   + https://mgu654\.mediapackage\.us\-east\-1\.amazonaws\.com/in/v1/xmm9s/channel

   + 883hdux

   + 634hjik 

1. Do not close this web browser yet\.

## Step 3: Create an Input<a name="getting-started-step3"></a>

You must create an input; this input describes how the source video asset will be provided to AWS Elemental MediaLive\. In this tutorial, you will create an RTP input\. 

You must also create an input security group for the input\. This input security group applies the rule "only this specific IP address \(an IP address that you own\) can push to this input on AWS Elemental MediaLive"\. Without the protection of this rule, any third party could push content to an AWS Elemental MediaLive input if they knew the IP address and port of the input\. 

1. Using your IAM credentials, sign in to the AWS Elemental MediaLive console at https://console\.aws\.amazon\.com/medialive?region="region"\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, type "My RTP push"\.

1. For **Input type**, choose **RTP**\. 

1. In **Input security group**, choose Create new\. 

1. In **New security group**, type or paste the IP address that you noted in step 1\. Enter the address as a CIDR\. For example, 192\.0\.2\.0/32\.

1. Choose **Create input security group**\.

1. Choose **Create** to create the input\.

   AWS Elemental MediaLive adds the input to the list of inputs and automatically creates two destinations \(one primary and one redundant\)\. These destinations include the port 5000\. For example, rtp://198\.51\.100\.0:5000 and rtp://198\.51\.100\.44:5000\. These are the two locations where the upstream system must push the source\. 

1. Make a note of these two addresses: you will need them in step 8\.

## Step 4: Attach the Input<a name="getting-started-step4"></a>

Now you start creating a channel\. The first step in creating a channel is to identify the input \. The channel contains the details that instruct AWS Elemental MediaLive how to transcode \(decode and encode\) and package that input into specific outputs\.

1. On the console, choose **Channels** in the navigation pane\.

1. In the content pane, choose **Create channel**\. 

1. In the **Channel and input details** pane, in **General info**, in **Channel Name**, type "Test channel"\.

1. In **Role ARN**, type the ARN of the role you created when you set up permissions for your AWS account\. For example, 

   arn:aws:iam::736754895224:role/AllowMediaLiveAccessRole\.

1. Select **Remember ARN**\.

1. In the **Attach input** section, in **Input**, choose "My RTP push" \(the input you created\)\. More fields appear\.

1. In **Audio** selectors, choose **Add audio selectors**\.

1. In **Audio selector name**, type "My audio source"\.

   There is no need to complete any other fields on this panel\. Specifically:

   + There is no need to create a video selector: when the channel starts, AWS Elemental MediaLive will automatically select the video \(or the first video\) in the input\.

   + In the audio selector, there is no need to specify the PID or language: when the channel starts, AWS Elemental MediaLive will automatically select the first audio, which is acceptable for this tutorial\. 

   + There is no need to create a captions selector\. Typically you will include captions in the channel configuration, but in this tutorial we are omitting them\.

## Step 5: Create an HLS Output Group<a name="getting-started-step5"></a>

1. In the navigation bar, move down to **Output groups** and choose **Add**\. 

1. Choose **HLS** and choose **Confirm**\. 

1. In **Name**, type "MyHLS"\. 

1. In **CDN settings**, choose **Hls webdav**\. This is the connection that AWS Elemental MediaPackage \(the downstream system for the channel output\) uses\. 

   Leave the defaults for all the other CDN fields\.

1. In **HLS group destination A**, in **URL**, type or paste the first input URL that AWS Elemental MediaPackage created for you in step 2\. For example, https://39fuo4\.mediapackage\.us\-east\-1\.amazonaws\.com/in/v1/88dpie/channel\. 

1. In **Credentials**, in **Username**, type or paste the username that corresponds to this URL\. For example, ue739wuty\.

1. In **Password**, choose **Create new parameter**\.

1. In **Name**, type "DestinationA\_MyHLS"\. 

1. In **Password**, type or paste the password that corresponds to the URL\. For example, due484u\.

1. Click **Create new parameter**\.

   You have created a parameter that holds the password\. The parameter is stored in the Amazon EC2 Systems Manager Parameter Store\. For more information, see [[ERROR] BAD/MISSING LINK TEXT](about-EC2Password.md)\.

1. In **HLS group destination B**, in **URL**, type or paste the second input URL that AWS Elemental MediaPackage created for you in step 2\. For example, https://mgu654\.mediapackage\.us\-east\-1\.amazonaws\.com/in/v1/xmm9s/channel\. 

1. In **Credentials**, in **Username**, type or paste the username that corresponds to this URL\. For example, 883hdux\.

1. In **Password**, choose **Create new parameter**\.

1. In **Name**, type "DestinationB\_MyHLS"\. 

1. In **Password**, type or paste the password that corresponds to the URL\. For example, 634hjik\.

1. Click **Create new parameter**\.

   You have created a parameter that holds this second password\. This parameter is also stored in the Amazon EC2 Systems Manager Parameter Store\. 

1. Leave the default values in all other fields on this pane\.

## Step 6: Set up the Output and Encodes<a name="getting-started-step6"></a>

1. In the navigation pane, choose **Output 1**\. This output was automatically added when you created the output group\. In addition, the output was automatically set up with one video and one audio, as shown in **Stream settings**\. 

1. In **Stream settings** choose Video\.

1. In **Video description name**, change the default name to "H264 video"\.

   Leave the remaining fields with the default values\. Specifically, leave Width and Height empty in order to use the same width as the input\.

1. In **Stream settings** choose **Audio**\.

1. In **Audio description name**, change the default name to "AAC audio"\.

1. In Audio selector name, type the audio selector you created in step 4, that is "My audio source"

   Leave the remaining fields with the default values\. Specifically, leave Codec settings as AAC\.

## Step 7: Save<a name="getting-started-step7"></a>

1. At the bottom of the navigation pane, choose Create channel\. 

   The channel section reappears and shows the newly created channel, named "MyHLS"\. The State changes to Creating, then Ready\.

1. Stay on this pane for now\.

## Step 8: Start the Upstream System and the Channel<a name="getting-started-step8"></a>

1. In your upstream system, start streaming the video sources that you set up in step 1\. Set them up to push to the two destinations you noted in step 3\. For example, rtp://198\.51\.100\.0:5000 and rtp://198\.51\.100\.44:5000\. 

1. On the channels list, select the channel\.

1. Choose Start\. The channel State changes to Starting, then to Running\.

1. Switch to the web browser tab or window where the AWS Elemental MediaPackage is displayed\. 

1.  Choose the channel link \(not the radio button\)\. On the details page, under Endpoints, choose Play\. A preview window appears\. Start the video\. The output from AWS Elemental MediaLive starts playing\.

## Step 9: Clean up<a name="getting-started-step9"></a>

To avoid extraneous charges, delete this channel and input when you have finished working with it\.

1. On the Channels page, select the channel\.

1. If needed, choose Stop\.

1. Choose Delete\.

1. On the Inputs page, select the input\.

1. Choose Delete\.