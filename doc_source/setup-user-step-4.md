# Step 4: Create the Groups<a name="setup-user-step-4"></a>

Any person who is an administrator can perform this procedure\. Follow the procedure once, when setting up users for production\. 

After you identify the different sets of users that your deployment requires, you must create a group for each set\. 

**To create the groups**

1. In IAM, choose **Groups**, and then use the **Create New Group Wizard** to create a group for each set of users that you identified in [Step 2: Identify Categories of Users](setup-user-step-2.md)\. See [http://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups_create.html](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups_create.html) and follow the steps for creating groups using the console\.

   As a best practice, assign group names that start with the service name, `medialive`\.

1. The **Create New Group Wizard** includes a step for attaching policies to the group as you create it\. Make sure to attach the managed and custom policies that you have identified\.

The following example assumes that you created a group called `medialivebasicusers` and associated the two custom policies plus one managed policy\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/usersetup_group+policies.png)