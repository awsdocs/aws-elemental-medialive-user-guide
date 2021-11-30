# Setting up: IAM permissions for AWS Elemental MediaLive for a production environment<a name="setting-up-for-production"></a>

This chapter provides procedures for setting up users and other AWS identities so that they can use AWS Elemental MediaLive in a production environment\. It describes options for imposing restricted controls on users, so that you can set up permissions that conform with the security policies and procedures of your organization\.

Before you follow these procedures, do the initial setup described in [Setting up: IAM permissions for AWS Elemental MediaLive](setting-up.md)\. Those instructions show you how to grant broad permissions to users for non\-production environments\. Then return to this chapter to create limited permissions for a production environment\.

**Note**  
For part of the setup described in this chapter, you use the AWS Identity and Access Management \(AWS IAM\) service to create user and administrator identities\. There might be features of IAM, such as cross\-account access, that are not covered in this chapter but are appropriate and useful to your deployment\. For information about all IAM features, see the [AWS IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.

In this chapter, we assume the following:
+ 

You are now moving from experimenting with MediaLive to using MediaLive in a production environment\.
+ You have followed the procedures in [Setting up: IAM permissions for AWS Elemental MediaLive](setting-up.md) to sign up for MediaLive and to create a full\-access administrator user\. 
+ You have followed the procedures in [Creating a non\-administrator IAM user](preproduction-set-up-users.md) and are therefore familiar with the process for creating IAM users and IAM groups using the IAM console\.

This chapter also describes the AWS services that integrate with or depend on MediaLive\. For some of these services, you must grant permissions so that users can access the services and use them with MediaLive\. For other services, you don't need to grant permissions because the services are fully integrated with MediaLive\. Following is a list of the AWS services that are covered in this chapter:
+ AWS CloudTrail
+ Amazon CloudWatch
+ Amazon CloudWatch Events
+ Amazon CloudWatch Logs
+ Amazon Elastic Compute Cloud \(Amazon EC2\)
+ AWS IAM
+ AWS Elemental MediaConnect
+ AWS Elemental MediaPackage
+ AWS Elemental MediaStore
+ AWS Resource Groups \(Resource Group Tagging\)
+ Amazon Simple Notification Service \(Amazon SNS\)
+ Amazon Simple Storage Service \(Amazon S3\)
+ AWS Systems Manager

The following sections describe how to grant permissions to MediaLive and, if needed, the other AWS services\.

**Topics**
+ [Setting up administrators and users](user-and-admin-setup.md)
+ [Creating an administrator user with limited access](setting-up-restricted-admin.md)
+ [Creating a non\-administrator user](set-up-users.md)
+ [Setting up AWS Elemental MediaLive as a trusted service](setup-medialive-trusted-service.md)
+ [Reference: summary of non\-administrator user access requirements](setup-users-step-1-summary.md)
+ [Reference: summary of requirements for the MediaLive trusted entity](trusted-entity-requirements.md)