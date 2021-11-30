# Setting up administrators and users<a name="user-and-admin-setup"></a>

You must set up each person who will use AWS Elemental MediaLive as a IAM user\. It is useful to split user identities into three general groups: 
+ Full\-access administrator users\. These users have full read/write access to all AWS services, users, and resources, including broad permissions in IAM\.

   You already created this user when you followed the procedure in [Creating an administrator IAM user](preproduction-create-iam-admin.md)\.
+ Administrators with limited access\. Typically, these users have more permissions than a non\-administrator user, but they don't have broad permissions in IAM\. 

  See [Creating an administrator user with limited access](setting-up-restricted-admin.md)\. 
+ Non\-administrator users or "regular users\." Typically, these users have broad permissions to MediaLive and to some of the services, such as MediaConnect, that MediaLive interacts with\. These users have very limited permissions in IAM\.

   See [Creating a non\-administrator user ](set-up-users.md)\. 

We recommend that you set up most users as non\-administrator users\. Set up only highly trusted users as administrator users\.