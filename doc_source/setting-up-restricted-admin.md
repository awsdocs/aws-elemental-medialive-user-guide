# Creating an Administrator User with Limited Access<a name="setting-up-restricted-admin"></a>

If you are a full\-access administrator, you can create other administrator users and assign each one a different level of access\. These administrator users have more access than non\-administrator users \("regular" users\), but they have less access than full\-access administrator users\. They can use AWS Elemental MediaLive in the same way as regular users, but they can also create non\-administrative users and set up some of the services that MediaLive integrates with\. 

For example, you might create an administrator user with the following access:
+ For MediaLive and services that integrate with MediaLive, the administrator has the same access as regular users\.
+ For services that require some setup to work with MediaLive, the administrator has more access than regular users\. 
+ For IAM, the administrator has more access than regular users, but less than full\-access administrators\.

The following procedure shows how to create an administrative user who has limited access\. You start by creating a custom policy with a name such as `MediaLiveAdminAccess`, creating a group called **MediaLiveAdministrators**, and attaching the policy to the group\. Next, you create the administrator user and add the user to the group\. The procedure assumes that the new administrator user does not need permissions to troubleshoot issues with MediaLive other than access issues\. 

**To create a custom policy for a MediaLive administrator**

1. Sign in to the AWS Management Console as a full\-access administrator, and open the IAM console at [https://console.aws.amazon.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Policies**, and then choose **Create policy**\. On the **Create policy** page, choose the **Visual editor** tab\. This tab is a policy generator that lets you build a policy by selecting actions from a list to add them to the policy\. 

1. Read the table at the end of this procedure, and create a policy that gives access to the actions that aren't already covered by an existing policy\. You don't need to create a policy when we suggest using an existing policy\. For information about the purpose of these actions, see [Step 1: Identify Requirements for Permissions for Users](setup-user-step-1.md)\.

1. To create the policy, follow the prompts on the console\. Here are some tips for creating the policy:
   + You can create one policy that covers several services\. You don't need to create a policy for each separate service\. To create a policy for several services, choose the actions for one service, and then choose **Add additional permissions** at the bottom of the page to set up another service\. You might need to move both of the vertical scroll bars to the bottom to display this link\. 
   + If you do choose to create one policy that covers several services, you might choose to create the policy with actions for one service, save it, then edit the policy to add permissions for another service, and so on\. 
   + You can choose the **Import managed policy** button to import an existing policy into this policy\. The policy actions are copied over \(the policy is *not* copied by reference\), so after importing you can add and remove actions if you want\.

   For full instructions on creating a custom policy, see the [https://docs.aws.amazon.com/IAM/latest/UserGuide/](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.

   The following table shows which actions to include in the policy in order to grant the identified access to the user\.    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/setting-up-restricted-admin.html)

**To create a group for your custom policy or policies**

1. If necessary, sign in to the AWS Management Console as a full\-access administrator, and open the IAM console at [https://console.aws.amazon.com/iam/](https://console.aws.amazon.com/iam/)\. \(You might still be signed in\.\)

1. In the navigation pane, choose **Groups**\. Follow the prompts to create a group with a name such as **MediaLiveAdministrators**\. 

1. Attach the policy or policies that apply to this administrator\. 

For full instructions on creating a group and attaching a policy, see the [https://docs.aws.amazon.com/IAM/latest/UserGuide/](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.

**To create an administrator user and add the user to your group**

1. If necessary, sign in to the AWS Management Console as a full\-access administrator, and open the IAM console at [https://console.aws.amazon.com/iam/](https://console.aws.amazon.com/iam/)\. \(You might still be signed in\.\)

1. In the navigation pane, choose **Users**\. Follow the prompts to create a user using the name of the person who will be the administrator\.

1. In the step to set permissions for the user, choose **Add user to group**, and then select the group that you created\.

1. Follow the prompts to finish creating the user\.

For full instructions for creating an administrator, see the [https://docs.aws.amazon.com/IAM/latest/UserGuide/](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.