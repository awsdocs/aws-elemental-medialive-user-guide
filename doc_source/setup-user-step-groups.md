# Step 2: Create an IAM Group<a name="setup-user-step-groups"></a>

The procedure in this section shows how to create an IAM group and attach policies\. Anyone with IAM administrator\-level credentials can perform the procedure\. Perform this procedure once, at initial setup\. Before you start the procedure, you should have already created the two policies in [Step 1: Create Customer Managed Policies](setup-user-step-policies.md)\.

**To create a group**

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Groups**, and then choose **Create New Group**\. 

1. On the **Set Group Name** page, for **Group Name**, enter **MediaLivePowerUsers**, and then choose **Next Step**\.

1. On the **Attach Policy** page, select the check boxes for the following policies:
   + **MediaLivePowerAccess** \(customer managed policy\)
   + **MediaConnectPowerAccess** \(customer managed policy\)
   + **MediaLiveTrustedEntityAccess** \(customer managed policy\)
   + **CloudWatchReadOnlyAccess** \(AWS managed policy\)
   + **CloudWatchEventsFullAccess** \(AWS managed policy\)
   + **CloudWatchReadOnlyAccess **\(AWS managed policy\)
   + **AmazonEC2FullAccess** \(AWS managed policy for access to AWS Virtual Private Network\)
   + **AWSElementalMediaPackageFullAccess** \(AWS managed policy\)
   + **ResourceGroupsandTagEditorFullAccess** \(AWS managed policy\)
   + **AmazonSSMFullAccess** \(AWS managed policy for access to Amazon EC2 Systems Manager\)
   + **AmazonSNSFullAccess** \(AWS managed policy\)

1. Choose **Next Step**, review your information, and then choose **Create Group**\.

This diagram shows how the policies and group are associated\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/preprod_usersetup_group+policies.png)