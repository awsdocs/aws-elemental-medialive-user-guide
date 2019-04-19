# Creating an Input Security Group<a name="create-input-security-groups"></a>

You create an input security group and then attach it to a "push" input when you create or edit that input\. 

**To create an input security group**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Input security groups**\. 

1. On the **Input security groups** page, choose **Create input security group**\. 

1. For **New security group**, type one or more IPv4 CIDR blocks\. Each CIDR block must include a subnet mask\. Separate the entries with commas, or type each entry on a separate line\. 

   Each item in the list represents one whitelist rule, even if it encompasses several individual addresses\. For example, each of the following examples counts as one rule: 

   192\.0\.2\.0/24

   192\.0\.2\.111/32

1. In the **Tags **section, create tags if you want to associate tags with this input security group\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\.

1. Choose **Create**\.