# Creating a non\-administrator IAM user<a name="preproduction-set-up-users"></a>

This section shows how to create non\-administrator IAM users and grant those users the following permissions:
+ Full read/write access to the following AWS services and features:
  + AWS Elemental MediaLive
  + AWS Elemental MediaConnect
  + AWS Elemental MediaPackage
  + Amazon CloudWatch
  + Amazon CloudWatch Events
  + Amazon CloudWatch Logs
  + Amazon EC2
  + AWS Systems Manager
  + AWS Resource Groups 
  + Amazon SNS
  + Amazon VPC 
+ Limited access to AWS IAM\. Users of AWS Elemental MediaLive need some access to IAM in order to use the MediaLive console to set up MediaLive as a trusted entity\. This setup is always required when using MediaLive\. For more information, see [Setting up AWS Elemental MediaLive as a trusted service](preproduction-trusted-entity.md)\.

**Warning**  
These permissions are broad\. You should set up only a few users with these permissions and only for the pre\-production period of using MediaLive\. For information about setting up users for standard production use, see [Setting up: IAM permissions for AWS Elemental MediaLive for a production environment](setting-up-for-production.md)\. 

To set up an IAM user, you follow three main steps:
+ Create customer managed policies\.
+ Create a group and attach the policies to the group\.
+ Create users and add the users to the group\.

Policies grant permissions\. Policies are attached to a group\. Users belong to a group\. Therefore, the users have the permissions of the policies that are attached to the group\.

The following diagram shows this relationship\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/usersetup_generic_policy_group_user.png)

**Topics**
+ [Step 1: Create customer managed policies](setup-user-step-policies.md)
+ [Step 2: Create an IAM group](setup-user-step-groups.md)
+ [Step 3: Create or add an IAM user to your group](setup-user-step-create-user.md)