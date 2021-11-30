# Step 3: Create an input<a name="getting-started-step3"></a>

You must create an input\. the input defines how the upstream system provides the source video stream to MediaLive\. in this tutorial, you create an rtp input\. 

You must also create an input security group for the input\. this input security group applies the rule "only this specific IP address \(an IP address that you own\) can push to this input on MediaLive\." without the protection of this rule, any third party could push content to an MediaLive input if they know the IP address and port of the input\. 

**To create an input and input security group**

1. Sign in to the AWS Management Console and open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input name**, enter **my rtp push**\.

1. For **Input type**, choose **rtp**\. 

1. in the **Input security group** section, choose **Create**\. 

1. In the text box, enter the IP address that you noted in [Step 1: Set up the upstream system](getting-started-step1.md) of this tutorial\. Enter the address as a CIDR block\. for example, **203\.0\.113\.111/32** and **203\.0\.113\.112/32**\.

1. Choose **Create input security group**\.

1. Choose **Create** to create the input\.

   MediaLive adds the input to the list of inputs and automatically creates two destinations \(one primary and one redundant\)\. these destinations include the port 5000\. for example, **rtp://198\.51\.100\.10:5000** and **rtp://192\.0\.2\.131:5000**\. these are the two locations where the upstream system must push the source\. 

1. make a note of these two addresses because you will need them in [Step 10: Start the upstream system and the channel](getting-started-step8.md)\.