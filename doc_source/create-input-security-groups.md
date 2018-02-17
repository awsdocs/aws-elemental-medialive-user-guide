# Creating an Input Security Group<a name="create-input-security-groups"></a>

To create an input security group:

1. Open the AWS Elemental MediaLive console at https://console\.aws\.amazon\.com/medialive?region="region"\.

1. In the navigation pane, choose **Input security groups**\. 

1. On the **Input security groups** page, choose **Create input security group**\. 

1. For **New security group**, type one or more IPv4 CIDR blocks\. Each CIDR block must include a subnet mask\. Separate the entries with commas, or type each entry on a separate line\. 

   Each item in the list represents one whitelist rule, even if it encompasses several individual addresses\. For example, each of the following examples counts as one rule: 

   192\.0\.2\.0/24

   192\.0\.2\.111/32

1. Choose **Create**\.