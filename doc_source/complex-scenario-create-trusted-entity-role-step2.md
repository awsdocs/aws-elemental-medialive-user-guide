# Step 2: Create Policies<a name="complex-scenario-create-trusted-entity-role-step2"></a>

Any person who is an administrator can create a policy\. 

In [Step 1: Determine the Access Requirements](complex-scenario-create-trusted-entity-role-step1.md), someone in your organization identified the policy or policies that you need to create\. 

Create those policies now in IAM\.

**To create a custom policy for the MediaLive trusted entity role**

1. If necessary, sign in to the AWS Management Console as a full\-access administrator, and open the IAM console at [https://console.aws.amazon.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Policies**, and then choose **Create policy**\. On the **Create policy** page, choose the **Visual editor** tab\. This tab is a policy generator that lets you build a policy by selecting actions from a list to add them to the policy\. 

   To create the policy, follow the prompts on the console\. Here are some tips for creating the policy:
   + You can create one policy that covers several services\. You don't need to create a policy for each separate service\. To create a policy for several services, choose the actions for one service, and then choose **Add additional permissions** at the bottom of the page to set up another service\. \(You might need to move both of the vertical scroll bars to the bottom to find **Add additional permissions**\.\) 
   + You can choose the **Import managed policy** button to import an existing policy into this policy\. The policy actions are copied over \(the policy is *not* copied by reference\), so after importing you can add and remove actions if you want\.

   For full instructions on creating a custom policy, see the [https://docs.aws.amazon.com/IAM/latest/UserGuide/](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.

To create the policy, follow the prompts on the console\. Here are some tips for creating the policy:
+ You can create one policy that covers several services\. There is no need to create a policy for each separate service\. To create a policy for several services, choose the actions for one service, and then choose the **Add additional permissions** button at the bottom of the screen to set up another service\. You may need to move both the vertical scroll bars to the bottom to reveal this button\. 
+ You can choose the **Import managed policy** button to import an existing policy into this policy\. The policy actions are copied over \(the policy is *not* copied by reference\), so after importing you can add and remove actions if you want\.

For full instructions on creating a custom policy, see the [https://docs.aws.amazon.com/IAM/latest/UserGuide/](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.