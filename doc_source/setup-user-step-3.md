# Step 3: Create the Custom Policies<a name="setup-user-step-3"></a>

Any person who is an administrator can perform this procedure\. Follow this procedure once, when setting up users for production\. 

After you identify the different collections of operations that your sets of users require, you must determine which collections have a corresponding managed policy or custom policy that already exists, and which require a new custom policy\. 

**To identify and create custom policies**

1. Look at each set of users that you identified, and look at the collections of operations for those users\. For each service, determine which collections have a corresponding managed policy and which require a custom policy\. 

   For example, for CloudWatch Events, there is a managed policy called `CloudWatchEventsFullAccess` that corresponds to "events:\*"\. But there is no policy that contains only the operations required to create a password parameter\. You must create a custom policy for that\. 

1. In IAM, create custom policies as applicable, using the IAM policy generator\. This generator lets you choose the service from a list, and then choose operations from a list\. As a best practice, give the policy a name that starts with the service name, `medialive`\.

   To create the policy, follow the prompts on the console\. Here are some tips for creating the policy:
   + You can create one policy that covers several services\. You don't need to create a policy for each separate service\. To create a policy for several services, choose the actions for one service, and then choose **Add additional permissions** at the bottom of the page to set up another service\. \(You might need to move both of the vertical scroll bars to the bottom to find **Add additional permissions**\.\)
   + You can choose **Import managed policy** to import an existing policy into this policy\. The policy actions are copied over \(the policy is *not* copied by reference\), so after importing you can add and remove actions if you want\.

   For detailed instructions for creating a policy, see [https://docs.aws.amazon.com/IAM/latest/UserGuide/](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.

The following example assumes that you created two custom policies\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/usersetup_policies.png)