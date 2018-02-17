# Creating an RTMP Push Input<a name="rtmp-push-input"></a>

1. Open the AWS Elemental MediaLive console at https://console\.aws\.amazon\.com/medialive?region="region"\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, type a name\.

1. For **Input type**, choose **RTMP \(push\)**\. 

1. In the **Input security group** section, specify a group to associate with this push input\. You can choose an existing group, or you can create a group\. For more information about security groups, see [[ERROR] BAD/MISSING LINK TEXT](working-with-input-security-groups.md)\. 

1. In the **Input destinations** section, type the final portion of the two destination locations \(one primary and one redundant\) on AWS Elemental MediaLive\. For example, `movies/classic`\. Don't include a leading slash\. For example, don't type `/movies/classic`\. 

   Typically, you enter the same value in both destinations; the difference in the two destinations will exist in the network portion that will be auto\-generated\. 

1. Choose **Create**\.

1. AWS Elemental MediaLive adds the input to the list of inputs and automatically creates two destinations ; the destinations include the final portion you specified\. These destinations include the port 1935\. For example, rtmp://198\.51\.100\.0:1935/movies/classic and rtmp://198\.51\.100\.66:1935/movies/classic\. These are the two locations where the upstream system must push the source\. 

   Provide the upstream system with these locations\.