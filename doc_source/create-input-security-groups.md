# Creating an input security group<a name="create-input-security-groups"></a>

You create an input security group to specify a list of access rules\. When you create a push input, you must attach an input security group, in order to restrict access to the input

You can include up to 10 rules \(IP address ranges or CIDR blocks\) in one input security group\.

You can attach the same input security group to any number of inputs\.

**To create an input security group**

1. Identify the IP addresses that the upstream systems will push from\. These IP addresses might be on the public internet or they might be on your LAN or WAN\.

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Input security groups**\. 

1. On the **Input security groups** page, choose **Create input security group**\. 

1. For **New security group**, type one or more IPv4 CIDR blocks\. 

   Each CIDR block must include a subnet mask\. In the examples below, the subnet mask is the */nn* portion\. 

   Separate the entries with commas, or type each entry on a separate line\. 

   You might not know how to form a CIDR block for your range of IP addresses\. If so, search on the internet for "IP CIDR calculator" to find an online converter tool\.

1. In the **Tags **section, create tags if you want to associate tags with this input security group\. For more information, see [Tagging AWS Elemental MediaLive resources](tagging.md)\.

1. Choose **Create**\.

**Example 1**  
192\.0\.2\.0/24

This CIDR block covers all IP addresses that start with *192\.0\.2*

**Example 2**  
192\.0\.2\.111/32

This CIDR block covers the single IP address *192\.0\.2\.111*