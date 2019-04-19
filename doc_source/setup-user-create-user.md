# Create a User<a name="setup-user-create-user"></a>

Typically, you create a new user identity for an AWS user only if a person does not have an existing identity\. If the person already has a user identity, modify their access instead\.

**To create a user**

1. Make sure that you know which group \([Step 4: Create the Groups](setup-user-step-4.md)\) that you want to add each user to\. Make sure that you have already created this group \([Step 4: Create the Groups](setup-user-step-4.md)\)\.

1. Sign in to the AWS Management Console as an administrator, and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Users**, and then choose **Add user**\.

1. On the **Add User** page, for **User name**, enter a name for the user\.

   For **Access type**, select **AWS Management Console access**\.

   For **Console password**, select **Custom password** and enter a password\. 

   For **Require password reset**, we recommend that you select the check box\.

1. Choose **Next: Permissions**\.

1. On the **Set permissions for user** page, choose **Add user to group**\.

1. Select the check box for the appropriate group for this user, and then choose **Next: Tags**\.

1. Add tags if your organization has a policy to create tags for users\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\. Then choose **Next: Review**\.

1. Choose **Create user**\. 

1. Optionally, choose **Send email** to send an email to this user\. Your local email client opens with a draft email that includes the user name and sign\-in URL\. 

1. Choose **Close** to return to the navigation pane\.

1. Provide the user with their password \(it is not included in the generated email\)\. You must provide the password in a way that complies with your organization's security guidelines\. 

The following example assumes that you created three users and associated all of them with the same group, `medialivebasicusers`\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/usersetup_group+policies+users.png)