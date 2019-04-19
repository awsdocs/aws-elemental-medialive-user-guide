# Step 3: Create or Add an IAM User to Your Group<a name="setup-user-step-create-user"></a>

The procedure in this section shows how to create or edit an IAM user identity\. Anyone with IAM administrator\-level credentials can perform the procedure\. Perform this step for each user\.

**Note**  
This procedure shows how to set up an IAM user for console access, but not for AWS CLI or AWS SDK access\. To set up for programmatic access, see the [https://docs.aws.amazon.com/IAM/latest/UserGuide/](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\. 

## Creating an IAM User and Adding the User to Your Group<a name="preproduction-create-user"></a>

Typically, you create an IAM user identity for an AWS user only if a person doesn't have an existing identity\. If the person already has an IAM user identity, you can [modify their access](#preproduction-modify-user) instead\.

**To create an IAM user and add the user to your group**

1. Sign in to the AWS Management Console as an administrator, and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Users**, and then choose **Add user**\.

1. On the **Add User** page, for **User name**, enter a name for the user\.

   For **Access type**, select **AWS Management Console access**\.

   For **Console password**, choose **Custom password**, and then enter a password\. 

   For **Require password reset**, we recommend that you select the check box\.

1. Choose **Next: Permissions**\.

1. On the **Set permissions for user** page, choose **Add user to group**\.

1. Select the check box for the **MediaLivePowerUsers** group that you created in [Step 2: Create a Group](setup-user-step-groups.md), and then choose **Next: Review**\.

1. Choose **Create user**\. 

1. Optionally choose **Send email** to send an email to this user\. Your local email client opens with a draft email that includes the user name and sign\-in URL\. 

1. Choose **Close** to return to the navigation pane\.

1. Provide the user with their password \(it is not included in the generated email\)\. You must provide the password in a way that complies with your organization's security guidelines\. 

Repeat the steps to add more IAM users\. As an example, the following diagram shows three IAM users that are associated with the same group, **MediaLivePowerUsers**\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/preprod_usersetup_group+policies+users.png)

## Adding an Existing IAM User to Your Group<a name="preproduction-modify-user"></a>

You can add an existing IAM user to a group that you create for AWS Elemental MediaLive, even if the user is already a member of other groups\. In this procedure, you add the user to the **MediaLivePowerUsers** group that you created in [Step 2: Create a Group](setup-user-step-groups.md)\.

For more information about IAM users and groups, see [https://docs.aws.amazon.com/IAM/latest/UserGuide/](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.

**To add an existing IAM user to your group**

1. Sign in to the AWS Management Console as an administrator, and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Users**\.

1. In the list of users, choose the user name \(don't choose the check box\)\. 

1.  On the **Summary** page, choose the **Groups** tab\. On the **Groups** tab, choose **Add user to groups**, and then select the **MediaLivePowerUsers** group that you created in [Step 2: Create a Group](setup-user-step-groups.md)\.

1. Choose **Add to Groups**\.

You now have a setup where an IAM user belongs to more than one group: the original groups and the group that you added\. If one of the groups has a policy that gives specific permissions to a given service or resource, and another group has a policy that gives different permissions, the policy with the *least permission* applies\. One situation in which this rule might apply is if the existing user currently has permissions in IAM that are broader than those in the **MediaLiveTrustedEntityAccess** policy that you created\. 