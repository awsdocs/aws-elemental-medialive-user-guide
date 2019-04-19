# Creating an Administrator IAM User<a name="preproduction-create-iam-admin"></a>

The procedures in this section show how to create an IAM user that has full read/write administrator permissions\. This administrator might be you or another person\. You set up an administrator by creating a group, and then creating a user that belongs to that group:
+ If your organization is new to AWS, follow both steps in this procedure: create the group, and then create the users for that group\.
+ If your organization is not new to AWS, then the group probably has already been created\. Follow only the second step to create users for that group\. 

**To create a full\-access administrator group**

1. Use your AWS account email address and password to sign in to the AWS Management Console as the AWS account root user\.

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Groups**, and then choose **Create New Group**\.

1. On the **Set Group Name** page, for **Group Name**, enter a name such as **Administrators**\. Choose **Next Step**\.

1. On the **Attach Policy** page, choose **Filter: Policy Type**, and then choose **Job function**\. 

1. In the policy list, select the check box for **AdministratorAccess**, and then choose **Next Step**\. 

1. On the **Review** page, review the information, and then choose **Create Group**\. 

Now that you have an administrator group, you are ready to create an IAM user and add the user to your group\.

**To add an IAM user to the full\-access administrator group**

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Users**, and then choose **Add user**\.

1. On the **Add User** page, for **User name**, enter a name such as **Administrator** or **Admin\_2** \(if **Administrator** has already been created\)\.

1. For **Access type**, select **AWS Management Console access**\.

   For **Console password**, choose **Custom password**, and then enter a password\. 

   If this administrator is not you, we recommend that you select **Require password reset**\.

1. Choose **Next: Permissions**\.

1. On the **Set permissions** page, choose **Add user to group**\.

1. Select the check box for the group that you created in the preceding procedure, and then choose **Next: Review**\.

1. Review the information, and then choose **Create user**\. To return to the navigation pane, choose **Close**\.

After you create this IAM user with administrator permissions, sign out and sign in again using the administrator credentials\. 

We highly recommend that from this point forward you always sign in using the IAM administrator credentials instead of your root user credentials, unless AWS requires you to use your root user credentials to perform certain operations\. For more information, see [AWS Tasks That Require AWS Account Root User Credentials](https://docs.aws.amazon.com/general/latest/gr/aws_tasks-that-require-root.html)\.

Repeat the procedure to set up more administrators \(as backups\), if needed\. Or anyone who is now set up as a full\-access administrator can set up more administrators\.