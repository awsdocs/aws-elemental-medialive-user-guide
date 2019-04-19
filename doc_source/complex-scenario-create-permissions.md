# Setting Up Permissions<a name="complex-scenario-create-permissions"></a>

This section applies if you have determined that your deployment requires the complex option for the trusted entity role, as described in [Options for Implementing the Role](scenarios-for-medialive-role.md)\. 

You must create a policy for the IAM service to set up these regular users with the permissions that they need for the complex option\. You must also attach that policy to the group that those regular users belong to\.

**To set up permissions**

1. Follow the steps in [Step 3: Create the Custom Policies](setup-user-step-3.md) with these differences:
   + Create a policy with a name such as `MediaLiveTrustedEntityRegularUserAccess`\.
   + Include only the actions that you identified in [Identifying Permissions](complex-scenario-identify-permissions.md)\.

1. In the group that you created or will create for regular users \(see [Step 4: Create the Groups](setup-user-step-4.md)\), include this policy\. 

1. Identify any other policies that relate to the IAM service, and detach them from this group\.