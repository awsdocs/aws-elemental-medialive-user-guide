# Creating a non\-administrator user<a name="set-up-users"></a>

This section describes how to create non\-administrator users \("regular users"\) by using IAM to create groups, attach policies to each group, and add the users to the group\. 

If you are new to AWS or if you have been using AWS for only a few weeks, we recommend that you read this entire section\. 

If you have more experience using other AWS services, read [Step 1: Identify requirements for permissions for users](setup-user-step-1.md)\. Then, based on your decisions, modify or create policies and groups in the usual way\. 

**Summary of Steps**  
 To create IAM users with access to AWS Elemental MediaLive, you must perform several steps: 
+ Identify the permissions that users need for MediaLive and other services\.
+ Identify the different sets of users that you need\. Each set will become an IAM group\.
+ Identify the managed and custom policies that will provide the access required for the sets of users\. Create the custom policies\.
+ Create the groups that you have identified, and attach the managed and custom policies\.
+ Create each user and add them to the appropriate group\.

**Topics**
+ [Step 1: Identify requirements for permissions for users](setup-user-step-1.md)
+ [Step 2: Identify categories of users](setup-user-step-2.md)
+ [Step 3: Create the Custom Policies](setup-user-step-3.md)
+ [Step 4: Create the groups](setup-user-step-4.md)
+ [Step 5: Create or modify each IAM user](setup-user-step-5.md)
+ [Step 6: Setting up required data](setup-user-step-6.md)