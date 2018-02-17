# Creating an RTP Push Input<a name="rtp-push-input"></a>

You must create your input before you create the channel that ingests the input\. 

1. Open the AWS Elemental MediaLive console at https://console\.aws\.amazon\.com/medialive?region="region"\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, type a name\.

1. For **Input type**, choose **RTP**\. 

1. In the **Input security group** section, specify a group to associate with this "push" input\. You can choose an existing group, or you can create a group\. For more information about security groups, see [[ERROR] BAD/MISSING LINK TEXT](working-with-input-security-groups.md)\. 

1. Choose **Create**\.

1. AWS Elemental MediaLive adds the input to the list of inputs and automatically creates two destinations \(one primary and one redundant\)\. These destinations include the port 5000\. For example, rtp://198\.51\.100\.0:5000 and rtp://198\.51\.100\.44:5000\. These are the two locations where the upstream system must push the source\. 

   Provide the upstream system with these locations\. 