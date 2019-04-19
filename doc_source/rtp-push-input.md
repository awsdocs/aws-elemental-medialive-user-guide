# Creating an RTP Push Input<a name="rtp-push-input"></a>

Create your input before you create the channel that ingests the input\. 

**To create an RTP push input**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, enter a name\.

1. For **Input type**, choose **RTP**\. 

1. In the **Network mode** section, choose **Public**\.

1. In the **Input security group** section, specify a group to attach to this "push" input\. You can choose an existing group, or you can create a group\. For more information about security groups, see [Working with Input Security Groups](working-with-input-security-groups.md)\. 

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and automatically creates two endpoints on that input\. These endpoints include the port 5000\. For example:

   `rtp://203.0.113.19:5000` 

   `rtp://203.0.113.131:5000`\. 

   MediaLive always creates two endpoints: 
   + If the channel for this input will be set up as a standard channel, both endpoints will be used\. 
   + If the channel for this input will be set up as a single\-pipeline channel, only the first endpoint will be used\. MediaLive won't expect to receive content at the second endpoint\. 

1. Provide the upstream system with the following information:
   + If the channel for this input will be set up as a standard channel, provide both locations\. The upstream system must push the video streams to these locations\.
   + If the channel for this input will be set up as a single\-pipeline channel, provide only the first location\. The upstream system must push its one stream to this location\.