# Creating a CDI push input in Amazon VPC<a name="input-create-cdi-push"></a>

You create a CDI push input in Amazon Virtual Private Cloud \(Amazon VPC\) to push uncompressed video content from an upstream system that is on your VPC to MediaLive\. Create your input before you create the channel that ingests the input\. 

For information about the characteristics of CDI sources, see [Reference: Supported input containers and codecs](inputs-supported-containers.md)\. 

A CDI input is always a standard\-class input\. However, you can attach it to a standard channel or a single\-pipeline channel\. You should have already read [Implementing pipeline redundancy](plan-redundancy-mode.md), to decide the class of channel you want\. 

**Note**  
Make sure that the content provider is using the latest version of the [AWS CDI SDK](https://aws.amazon.com/media-services/resources/cdi/) on their upstream CDI source device\.

**To create a CDI push input from Amazon VPC**

1. You should have already worked with the Amazon VPC user to [set up the VPC for your content](cdi-push-vpc-upstream.md)\. Make sure that the Amazon VPC user gives you the following information: 
   + The ID of the VPC\.
   + The IDs of the two subnets\.
   + The IDs of the security groups for the subnet or subnets\.

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. Complete the **Input details** section:
   + **Input** name – enter a name\.
   + **Input type** – choose **AWS CDI**\. 

1. Complete the **VPC settings** section:
   + Choose **Select subnets and security groups**\. 
   + For **Subnets**, choose one of the subnets that you obtained\. The dropdown list shows subnets in all VPCs, identified as follows:

     `<subnet ID> <Availability Zone of subnet> <IPv4 CIDR block of subnet> <VPC ID> <Subnet tag called "Name", if it exists>`

     For example:

     **subnet\-1122aabb us\-west\-2a 10\.1\.128\.0/24 vpc\-3f139646 Subnet for MLive push inputs**

     If the list of subnets is empty, choose **Specify custom VPC**, and enter the subnet ID in the field\. \(You need to enter only the subnet ID, for example, **subnet\-1122aabb**\.\) 
   + In **Subnets**, choose the second subnet\. This second time, the dropdown list shows only the subnets in the same VPC as the first subnet\.
   + For **Security groups**, choose the security group or groups that you obtained, following the same process as for the subnets\. The dropdown list shows security groups belonging to the VPC that you chose, identified as follows:

     `<security group ID> <description attached to this security group> <VPC ID>`

     For example:

     **sg\-51530134 Security group for MLive push inputs vpc\-3f139646**

1. Complete the **Role ARN** section to choose a role for MediaLive to use with this input\. For more information, see [IAM role and ARN](#cdi-push-role-and-remember-arn)\. 

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and automatically creates two endpoints on that input\. These endpoints have a private IP address from the subnet range, and they specify port 5000\. For example:

   `10.99.39.23:5000`

   `192.0.2.54:5000` 

1. Provide the upstream system with these endpoints:
   + If you will set up the channel as a standard channel, provide both endpoints\. The upstream system must push the content to both endpoints\.
   + If you will set up the channel as a single\-pipeline channel, provide only the first endpoint\. The upstream system must push to this one endpoint\.

**Result of these procedures**  
As a result of this setup, each output of the upstream system has an IP address in one of the specified subnets in your VPC\. 

The CDI input has two IP addresses\. These addresses are fixed for the lifetime of the input, regardless of changes that occur \(such as modifying other information in the input, or attaching the input to a different channel\)\.

Each address is in one of those subnets\. In this way, the delivery of the content from the upstream system to MediaLive takes place within the security of the VPC\. 

For a description of this setup that includes a diagram, see [Result of this procedure](cdi-push-vpc-upstream.md#setup-result-cdi-vpc) in the section about setting up a CDI source\.

Keep in mind that with a push input, the upstream system must be pushing the video source to the input when you start the channel\. The upstream system does not need to be pushing before then\. 

## IAM role and ARN<a name="cdi-push-role-and-remember-arn"></a>

This section describes how to complete the **Role ARN** section on the **Create input** pane of the MediaLive console\.

You must choose a role for MediaLive to assume when it creates an RTP Push input\. To create the input, MediaLive must obtain the network interfaces for the two endpoints in the input\. These endpoints are in the CIDR range of the subnets that you identified\. As soon as you choose **Create** for this input, MediaLive requests these network interfaces from Amazon VPC\. The role that you choose ensures that MediaLive succeeds in its request to Amazon VPC\.

**Note**  
This section on the MediaLive console is identical to the **IAM role** section on the **Create channel** page \(also on the MediaLive console\)\. The difference in the two usages is that on the **Create input** page, you are attaching the role to the input\. On the **Create channel** page, you are attaching the role to the channel\. You can use the same role \(for example, the **MediaLiveAccessRole**\) in both usages\.

There are two general scenarios for choosing a role, depending on whether your organization has a designated administrator\.

### Your organization has a designated administrator<a name="cdi-push-role-scenario-1"></a>

Your organization might have an administrator who manages this service\. That administrator has likely set up one or more roles: 
+ Ask the administrator or your manager which role to use\. Or if only one role is listed in **Use existing role**, choose that role\. 
+ If the only role that is listed is **MediaLiveAccessRole**, choose that role\. In addition, if the **Update** button is displayed beside this role name, choose the button\. \(The button does not always appear, but whenever it does appear, choose it to refresh the role\.\)
+ If you want the selected role to appear first in the list next time, select **Remember ARN**\. 

### Your organization has no administrator<a name="cdi-push-role-scenario-2"></a>

Your organization might not have a designated service administrator\. In this case, if none of your colleagues have set up a suitable role, you might have to create one yourself and then choose it\. 
+ You can create the default role, called **MediaLiveAccessRole**\. To first check if someone else has already created this role \(only one person needs to create it for all users in your AWS account\), look at **Create role from template**:
  + If this option is grayed out, this task has been done\. In that case, choose **Use existing role**, and then choose **MediaLiveAccessRole** from the list\. 
  + If this option is not grayed out, choose **Create role from template**, and then choose **Create IAM role**\. Next, choose that role from the list\. If MediaLive does not let you create the role, speak to an AWS IAM administrator in your organization about your permissions\. 
+ If the **MediaLiveAccessRole** has already been created and the **Update** button is displayed beside it, choose the button\. \(The button does not always appear, but whenever it does appear, choose it to refresh the role\.\)
+ If you want the selected role to appear first in the list next time, select **Remember ARN**\.