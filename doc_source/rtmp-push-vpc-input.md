# Creating an RTMP Push Input in Amazon VPC<a name="rtmp-push-vpc-input"></a>

You create an RTMP push input in Amazon Virtual Private Cloud \(Amazon VPC\) to push content from an upstream system that is in your VPC to MediaLive\. Create your input before you create the channel that ingests the input\. 

**To set up the upstream system and the VPC**

1. Identify a VPC\. Make a note of the VPC ID\. For example:

   `vpc-3f139646`
**Note**  
We recommend that your organization create a VPC specifically for all AWS Media Services\. A single VPC will help to ensure the availability of IP addresses, help in setting up appropriate rules in the security groups, help in adhering to the two Availability Zone rule, and help to ensure that a network administrator doesn't accidentally delete elastic network interfaces\.

1. Identify two subnets in the VPC\. These rules apply to the subnets:
   + The two subnets must be in different Availability Zones\.
   + Each subnet must have a private CIDR block \(a range of IP addresses\)\.
   + Each subnet must have at least two unused addresses in that block—one for the upstream system and one for the MediaLive input\.
   + Any other RTP VPC inputs or RTMP VPC inputs that you create for use in the same channel as this input must be in subnets that are in the same Availability Zones as this input\. The two subnets of the new inputs can be different from the existing input, but the Availability Zones of those two subnets must be the same as the Availability Zones of this input\.

   Make a note of the subnet IDs\. For example:

   `subnet-1122aabb`

   `subnet-4455ccdd`

1. On your upstream system, set up two identical source streams \(if the channel for this input will be set up as a [standard channel](plan-redundancy-mode.md)\) or one source stream \(if it will be set up as a single\-pipeline channel\)\. Set up one source stream so that it has an output interface in one of the subnets, and the other so that it has an output interface in the other subnet\. 

1. Make sure that the two streams are identical in terms of resolution and bitrate\. 

1. Identify at least one security group for each subnet\. 
**Note**  
Don't confuse the security groups that belong to Amazon VPC with the input security groups that belong to MediaLive\.

   These rules apply to the security groups for each subnet:
   + The combined rules of the security groups must allow inbound traffic from the IP addresses of the upstream system in that subnet\.
   + The combined rules of the security groups must allow outbound traffic to port 3500\. 

1. Make a note of the IDs of the security group or groups\. For example:

   `sg-51530134`

1. Make a note of the following three characteristics of the source stream\. You will need this information to set up the channel:
   + The video codec
   + The resolution of the video—SD, HD, or UHD
   + The maximum input bitrate 

**To create an RTMP VPC push input**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, enter a name\.

1. For **Input type**, choose **RTMP \(push\)**\. 

1. In the **Network mode** section, choose **VPC**\.

1. In the **VPC settings** section, choose **Use existing VPC**\. For **Subnets**, choose one of the subnets that you identified\. The dropdown list shows subnets in all VPCs, identified as follows:

   `<subnet ID> <Availability Zone of subnet> <IPv4 CIDR block of subnet> <VPC ID> <Subnet tag called "Name", if it exists>`

   For example:

   **subnet\-1122aabb us\-west\-2a 10\.1\.128\.0/24 vpc\-3f139646 Subnet for MLive push inputs**

   If the list of subnets is empty, choose **Specify custom VPC** and enter the subnet ID in the field\. \(You need to enter only the subnet ID, for example, **subnet\-1122aabb**\.\) 

1. Choose the second subnet\. This second time, the dropdown list shows only the subnets in the same VPC as the first subnet\.

1. For **Security groups**, choose the security group or groups that you identified, following the same process as for the subnets\. The dropdown list shows security groups belonging to the VPC that you chose, identified as follows:

   `<security group ID> <description attached to this security group> <VPC ID>`

   For example:

   **sg\-51530134 Security group for MLive push inputs vpc\-3f139646 **

1. Complete the **Role ARN** section to choose a role for MediaLive to use with this input\. For more information, see [IAM Role and ARN](rtp-push-vpc-input.md#rtp-push-role-and-remember-arn)\. 

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and automatically creates two endpoints on that input\. These endpoints have a private IP address from the subnet range, and they specify port 1935\. For example:

   `rtmp://10.99.20.15:1935`

   `rtmp://192.0.2.53:1935`\. 

1. Provide the upstream system with these endpoints: 
   + If the channel for this input will be set up as a standard channel, provide both endpoints\. The upstream system must push the content to both endpoints\.
   + If the channel for this input will be set up as a single\-pipeline channel, provide only the first endpoint\. The upstream system must push to this one endpoint\.

**Result of These Procedures**

As a result of this setup, each output of the upstream system has an IP address in one of the specified subnets in your VPC\. The RTMP input has two IP addresses\. Each address is in one of those same subnets\. In this way, the delivery of the content from the upstream system to MediaLive takes place within the security of the VPC\.

Keep in mind that with a push input, the upstream system must be pushing the video source to the input when you start the channel\. The upstream system does not need to be pushing before then\. 

## IAM Role and ARN<a name="rtmp-push-role-and-remember-arn"></a>

This section describes how to complete the **Role ARN** section on the **Create input** pane of the MediaLive console\.

You must choose a role for MediaLive to assume when it creates an RTMP Push input\. In order to create the input, MediaLive must obtain the network interfaces for the two endpoints in the input\. These endpoints are in the CIDR range of the subnets that you identified\. As soon as you choose **Create** for this input, MediaLive requests these network interfaces from Amazon VPC\. The role that you choose ensures that MediaLive succeeds in its request to Amazon VPC\.

**Note**  
This section on the MediaLive console is identical to the **IAM role** section on the **Create channel** page \(also on the MediaLive console\)\. The difference in the two usages is that on the **Create input** page, you are attaching the role to the input\. On the **Create channel** page, you are attaching the role to the channel\. You can use the same role \(for example, the **MediaLiveAccessRole**\) in both usages\.

There are two general scenarios for choosing a role, depending on whether your organization has a designated administrator\.

### Your Organization Has a Designated Administrator<a name="rtmp-push-role-scenario1"></a>

Your organization might have an administrator who manages this service\. That administrator has likely set up one or more roles: 
+ Ask the administrator or your manager which role to use\. Or if only one role is listed in **Use existing role**, choose that role\. 
+ If the only role that is listed is **MediaLiveAccessRole**, choose that role\. In addition, if the **Update** button is displayed beside this role name, choose the button\. \(The button does not always appear, but whenever it does appear, choose it to refresh the role\.\)
+ If you want the selected role to appear first in the list next time, select **Remember ARN**\. 

### Your Organization Has No Administrator<a name="rtmp-push-role-scenario2"></a>

Your organization might not have a designated service administrator\. In this case, if none of your colleagues have set up a suitable role, you might have to create one yourself and then choose it\. 
+ You can create the default role, called **MediaLiveAccessRole**\. To first check if someone else has already created this role \(only one person needs to create it for all users in your AWS account\), look at **Create role from template**:
  + If this option is grayed out, this task has been done\. In that case, choose **Use existing role**, and then choose **MediaLiveAccessRole** from the list\. 
  + If this option is not grayed out, choose **Create role from template**, and then choose **Create IAM role**\. Next, choose that role from the list\. If MediaLive does not let you create the role, speak to an AWS IAM administrator in your organization about your permissions\. 
+ If the **MediaLiveAccessRole** has already been created and the **Update** button is displayed beside it, choose the button\. \(The button does not always appear, but whenever it does appear, choose it to refresh the role\.\)
+ If you want the selected role to appear first in the list next time, select **Remember ARN**\.