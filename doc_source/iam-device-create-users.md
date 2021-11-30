# Creating a non\-administrator user<a name="iam-device-create-users"></a>

This section describes how to create non\-administrator users and give those users limited permissions\. Any person who is an administrator can perform this procedure\.

You might have created some users and assigned policies to them\. This procedure has a different approach—it describes how to create a group that contains a policy, then add users to that group\. This approach ensures that all users are set up with the same permissions \(the permissions of the group\), which is particularly important if you later add more than one policy to the group\.

**Summary of Steps**  
You should create non\-administrator users and give them only the permissions that they need in order to work with AWS Elemental Link devices: 
+ Create a custom policy that gives users the permission that they need in order to work with devices\.
+ Create a group for your users, and attach the policy\.
+ Create each user and add them to the group\.

**Initial setup**  
The first time you perform this setup, you must create a custom policy, create a group, and then create users and add them to the group\.

**Subsequent setup**  
After you have performed the initial setup, then each time you want to add a user, you only need to create the user and add them to the existing group\.

**Topics**

**To create a custom policy**
+ In IAM, use the IAM policy generator to create a custom policy\. The policy generator lets you choose the service from a list, and then choose operations from a list\. As a best practice, give the policy a name that starts with the service name, `medialive`\. In the policy, include these MediaLive operations:
  + `AcceptInputDeviceTransfer`
  + `CancelInputDeviceTransfer`
  + `ListInputDeviceTransfers`
  + `RejectInputDeviceTransfer`
  + `TransferInputDevice`

  To create the policy, follow the prompts on the console\. For detailed instructions for creating a policy, see [https://docs.aws.amazon.com/IAM/latest/UserGuide/](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.

**To create a group**

1. In IAM, choose **Groups**, and then use the **Create New Group Wizard** to create one group that all of your users will belong to\. See [https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups_create.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups_create.html) and follow the steps for creating groups using the console\.

   As a best practice, give the group a name that starts with the service name, `medialive`\.

1. The **Create New Group Wizard** includes a step for attaching policies to the group as you create it\. Make sure to attach the policy that you created\.

**To create a user**

This procedure describes how to set up the user for console access, but not for AWS CLI or AWS SDK access\. To set up for programmatic access, see [https://docs.aws.amazon.com/IAM/latest/UserGuide/](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\. 

1. Make sure that you know which group that you want to add each user to\. Make sure that you have already created this group \([Step 4: Create the groups](setup-user-step-4.md)\)\.

1. Sign in to the AWS Management Console as an administrator, and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Users**, and then choose **Add user**\.

1. On the **Add User** page, for **User name**, enter a name for the user\. Complete the following fields:
   + For **Access type**, select **AWS Management Console access**\.
   + For **Console password**, select **Custom password** and enter a password\. 
   + For **Require password reset**, we recommend that you select the check box\.

1. Choose **Next: Permissions**\.

1. On the **Set permissions for user** page, choose **Add user to group**\.

1. Select the check box for the appropriate group for this user, and then choose **Next: Tags**\.

1. Choose **Create user**\. 

1. Optionally, choose **Send email** to send an email to this user\. Your local email client opens with a draft email that includes the user name and sign\-in URL\. 

1. Choose **Close** to return to the navigation pane\.

1. Provide the user with their password \(it is not included in the generated email\)\. You must provide the password in a way that complies with your organization's security guidelines\. 