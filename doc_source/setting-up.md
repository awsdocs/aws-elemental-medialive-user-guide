# Setting up: IAM permissions for AWS Elemental MediaLive<a name="setting-up"></a>

This chapter provides procedures for setting up users to work with AWS Elemental MediaLive\. It describes how to grant permissions that are appropriate for the period when you are experimenting with MediaLive, before you start using MediaLive in a production environment\. 

This chapter covers the following tasks:
+ Setting up one or more administrators for the service
+ Creating or modifying user identities that have permissions to access AWS Elemental MediaLive and ancillary services that MediaLive typically works with
+ Setting up MediaLive as a trusted service 

After you perform the procedures in this chapter, you and other users will have permissions that let you successfully follow the [Getting started with AWS Elemental MediaLive](getting-started.md)\. 

**Important**  
This chapter includes steps that grant broad permissions to AWS Elemental MediaLive and other services\. These permissions are known as AWS Identity and Access Management \(IAM\) permissions\. The permissions are intended to allow you and others in your organization to get started with MediaLive as quickly as possible\. These permissions are not suitable for assigning to a wide group of users or for users working in a production environment\.  
To set up users for production use of AWS Elemental MediaLive, see [Setting up: IAM permissions for AWS Elemental MediaLive for a production environment](setting-up-for-production.md)\. 

**Topics**
+ [Signing up for AWS Elemental MediaLive](setting-up-aws-sign-up-preproduction.md)
+ [Creating an administrator IAM user](preproduction-create-iam-admin.md)
+ [Creating a non\-administrator IAM user](preproduction-set-up-users.md)
+ [Setting up AWS Elemental MediaLive as a trusted service](preproduction-trusted-entity.md)