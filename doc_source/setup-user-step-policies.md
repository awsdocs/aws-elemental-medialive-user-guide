# Step 1: Create Customer Managed Policies<a name="setup-user-step-policies"></a>

The procedures in this section show how to create two IAM customer managed policies\. A customer managed policy is one that you create and manage\. \(IAM also includes AWS managed policies, which you can't change\.\) 

Anyone with IAM administrator\-level credentials can perform the procedures\. 

The first procedure shows how to create a policy called **MediaLivePowerAccess** that gives full read/write access to AWS Elemental MediaLive\.

The second procedure shows how to create a policy called **MediaConnectPowerAccess** that gives full read/write access to AWS Elemental MediaConnect\.

The third procedure shows how to create a policy called **MediaLiveTrustedEntityAccess** that gives access to six operations in AWS IAM\. These actions allow IAM users to create and update a trusted entity role for AWS Elemental MediaLive by setting the fields in the **IAM role** section on the **Channel and input details** page on the MediaLive console\.

**To create the MediaLivePowerAccess policy**

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Policies**, and then choose **Create policy**\. On the **Visual editor tab**, follow the prompts to create a policy with these options:
   + **Service**: **MediaLive**
   + **Actions**: **All MediaLive actions \(medialive\.\*\)**
   + **Resources**: This option is completed automatically
   + **Request conditions**: Omit this option

1. Choose **Review policy**\. 

1. On the **Create policy** page, for **Name**, enter **MediaLivePowerAccess**\.

1. For **Description**, optionally describe the purpose of this policy\. This helps you identify the policy on the dashboard\.

1. Choose **Create policy**\.

**To create the MediaConnectPowerAccess policy**

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Policies**, and then choose **Create policy**\. On the **Visual editor tab**, follow the prompts to create a policy with these options:
   + **Service**: **MediaConnect**
   + **Actions**: **All MediaConnect actions \(mediaconnect\.\*\)**
   + **Resources**: This option is completed automatically
   + **Request conditions**: Omit this option

1. Choose **Review policy**\. 

1. On the **Create policy** page, for **Name**, enter **MediaConnectPowerAccess**\.

1. For **Description**, optionally describe the purpose of this policy\. This helps you identify the policy on the dashboard\.

1. Choose **Create policy**\.

**To create the MediaLiveTrustedEntityAccess policy**

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Policies**, and then choose **Create policy**\. On the **Visual editor tab**, follow the prompts to create a policy with these options:
   + **Service**: **IAM**
   + **Actions**: In the filter box under **Specify the actions allowed in IAM**, search for and then select each of these actions:
     + **ListRoles**
     + **GetRolePolicy**
     + **CreateRole**
     + **PassRole**
     + **AttachRolePolicy**
     + **PutRolePolicy**
   + **Resources**: **All resources**
   + **Request conditions**: Omit this option

1. Choose **Review policy**\. 

1. On the **Create policy** page, for **Name**, enter **MediaLiveTrustedEntityAccess**\.

1. For **Description**, optionally describe the purpose of this policy\. This helps you identify the policy on the dashboard\.

1. Choose **Create policy**\.