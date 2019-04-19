# Creating a Non\-Administrator IAM User<a name="preproduction-set-up-users"></a>

This section shows how to create non\-administrator IAM users and grant those users the following permissions:
+ Full read/write access to the following AWS services and features:
  + AWS Elemental MediaLive
  + AWS Elemental MediaConnect
  + AWS Elemental MediaPackage
  + Amazon CloudWatch
  + Amazon CloudWatch Events
  + Amazon CloudWatch Logs
  + Amazon EC2
  + Amazon EC2 Systems Manager
  + AWS Resource Groups 
  + Amazon SNS
  + Amazon VPC 
+ Limited access to AWS IAM\. Users of AWS Elemental MediaLive need some access to IAM in order to use the MediaLive console to set up MediaLive as a trusted entity\. This setup is always required when using MediaLive\. For more information, see \*\.\*\.

**Warning**  
These permissions are broad\. You should set up only a few users with these permissions and only for the pre\-production period of using MediaLive\. For information about setting up users for standard production use, see [Setting Up AWS Elemental MediaLive Permissions for a Production Environment](setting-up-for-production.md)\. 

**To set up an IAM user, you follow three main steps**

1. Create customer managed policies\.

1. Create a group and attach the policies to the group\.

1. Create users and add the users to the group\.

Policies grant permissions\. Policies are attached to a group\. Users belong to a group\. Therefore, the users have the permissions of the policies that are attached to the group\.

The following diagram shows this relationship\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/usersetup_generic_policy_group_user.png)

**Topics**
+ [Step 2: Create an IAM Group](setup-user-step-groups.md)
+ [Step 3: Create or Add an IAM User to Your Group](setup-user-step-create-user.md)