# Step 2: Identify Categories of Users<a name="setup-user-step-2"></a>

After you have identified the permissions that your users need, you must identify the different categories of users that you need\. You identify different categories based on the different operations they should be allowed to perform\. 

This requirements analysis must be performed by a person in your organization who understands the AWS Elemental MediaLive workflows for your organization and the different AWS services that the workflows use\.

**To identify categories of users**

1. Refer to the sections in [Step 1: Identify Requirements for Permissions for Users](setup-user-step-1.md), and decide whether all of your users should have the same permissions on all the services or whether some users should have one set of permissions while other users have another set\.

1. Group these different categories into, giving each category a name\. 

1. When looking at operations, keep in mind that you could decide that no regular user should have certain permissions—only an administrator should have those permissions\. 

For example, perhaps you identify three categories of users:
+ Basic users –These users can start and stop channels and view metrics for channels, but have no write permissions\.
+ Read/write users – These users have nearly full permissions, but they can't create password parameters in AWS Systems Manager Parameter Store\.
+ Advanced users – These users have full permissions on the services identified in [Step 1: Identify Requirements for Permissions for Users](setup-user-step-1.md)\. They are nearly as powerful as a restricted administrator, except that they can't set up users\.