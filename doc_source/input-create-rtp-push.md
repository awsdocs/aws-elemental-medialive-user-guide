# Creating an RTP push input<a name="input-create-rtp-push"></a>

Create your input before you create the channel that ingests the input\. 

For information about the types of RTP inputs that MediaLive supports, see [Reference: Supported input containers and codecs](inputs-supported-containers.md)\. 

An RTP input is always a standard\-class input\. However, you can attach it to a standard channel or a single\-pipeline channel\. You should have already read [Implementing pipeline redundancy](plan-redundancy-mode.md), to decide the class of channel you want\.

**To create an RTP push input**
+ You should have already arranged with the video content provider to [set up the upstream system](rtp-push-upstream.md) for your content\. Make sure that the operator of the upstream system gives you the following information:
  + The sets of IP addresses where the source or sources for the content will appear on the public network\. You need this information to create the input security group that you attach to the RTP input\.

    For example:
    + For one source: `203.0.113.19, 203.0.113.58, 203.0.113.25`
    + For the other source: `198.51.100.19, 198.51.100.59, 198.51.100.21`

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. Complete the **Input details** section:
   + **Input** name – enter a name\.
   + **Input type** – choose **RTP**\. 

1. In the **Network mode** section, choose **Public**\.

1. In the **Input security group** section, specify a group to attach to this push input\. You can choose an existing group, or you can create a group\. For more information about security groups, see [Working with input security groups](working-with-input-security-groups.md)\. The security group must allow the public network IP addresses to push to MediaLive\. Following from the example in step 1, it must allow these addresses:

   203\.0\.113\.19, 203\.0\.113\.58, 203\.0\.113\.25, 198\.51\.100\.19, 198\.51\.100\.59, 198\.51\.100\.21

   For more information about security groups, see [Working with input security groups](working-with-input-security-groups.md)\. 

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and automatically creates two endpoints on that input\. These endpoints include the port 5000\. For example:

   `198.51.100.99:5000` 

   `192.0.2.18:5000`

   Note that the IP addresses are addresses that MediaLive creates\. They aren't the public addresses that you used in the security group\. For a diagram that shows the role of all the IP addresses, see [Result of this procedure](rtp-push-upstream.md#setup-result-rtp-push) in the section about setting up an RTP push source\.

   MediaLive always creates two endpoints: 
   + If you will set up the channel as a standard channel, both endpoints will be used\. 
   + If you will set up the channel as a single\-pipeline channel, only the first endpoint will be used\. MediaLive won't expect to receive content at the second endpoint\. 

1. Provide the upstream system with the following information:
   + If you will set up the channel as a standard channel, provide both locations\. The upstream system must push the video streams to these locations\.
   + If you will set up the channel as a single\-pipeline channel, provide only the first location\. The upstream system must push its one stream to this location\.

   For example, provide these addresses:

   `198.51.100.99:5000` 

   `192.0.2.18:5000`

**Result of this procedure**  
As a result of this setup, an RTP push input exists that specifies two URLs\. These URLs are fixed for the lifetime of the input, regardless of changes that occur \(such as modifying other information in the input, or attaching the input to a different channel\)\. 

The upstream system pushes the source content to these endpoints\.

Keep in mind that with a push input, the upstream system must be pushing the video source to the input when you start the channel\. The upstream system does not need to be pushing before then\. 

For a description of this setup that includes a diagram, see [Result of this procedure](rtp-push-upstream.md#setup-result-rtp-push) in the section about setting up an RTP source\.