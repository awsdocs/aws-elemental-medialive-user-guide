# Modify an Existing User<a name="setup-user-modify-user"></a>

If a user identity already exists for someone who will use AWS Elemental MediaLive, you can set them up for use in a production environment by modifying their user identity to make them a member of the relevant group \(in addition to the group or groups where they are already members\.\)

You need to know the group that each user needs to belong to; see [Step 4: Create the Groups](setup-user-step-4.md)\.

One situation in which it is very useful to modify an existing non\-administrator user is if you followed the procedures in [Setting Up AWS Elemental MediaLive](setting-up.md) to set up users for the period when you are experimenting with MediaLive\. Following that procedure, you created a policy called `MediaLiveAccessUser` and a group called `MediaLivePowerUsers.` You can now take away the broad permissions that you gave those users and "move" the users from the `MediaLivePowerUsers` group to one of the groups that you created in [Step 4: Create the Groups](setup-user-step-4.md)\. There is no need to delete these users and create them again\.

**To modify a user**

1. Sign in to the AWS Management Console as an administrator, and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Users**\.

1. In the list of users, choose the user name \(don't select the check box\)\. 

1. On the **Summary** page, choose the **Groups** tab:
   + To add this user to another group, on the **Groups** tab, choose **Add user to groups** and follow the prompts to choose the group\. 
   + To remove this user from a group, choose the **X** icon beside the group name and follow the prompts\.

     You might want to remove the user from the `MediaLivePowerUsers` group but keep them in groups that give access to other AWS services\.

   You might now have the setup where a user belongs to more than one group, the original groups and the groups that you added\. If one of the groups has a policy that gives specific permissions to a given service or resource, and another group has a policy that gives different permissions, the policy with the *least permission* applies\.