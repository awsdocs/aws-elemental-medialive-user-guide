# How the Trusted Entity Is Created and Attached<a name="complex-scenario-how-entity-handled"></a>

This section applies if you have determined that your deployment should implement the complex option for the trusted entity role, as described in [Options for Implementing the Role](scenarios-for-medialive-role.md)\. 

With complex options, the process for creating trusted entity roles and attaching a specific role when creating a channel typically works as follows: 
+ Process for creating a role – An administrator creates the roles using IAM\. They don't use the **IAM role** pane on the **Create channel** page on the AWS Elemental MediaLive console\. They create these roles as part of the initial deployment\.
+ Process for attaching a role – After the required roles are created, the administrator gives each regular user a list of the roles and the channels that each role applies to\. 

  Each user might have a different list of roles; they will have only the roles that apply to the channels that they work with\.

  When a user who has permission to create a channel is working on the **Create channel** page, they will display the **Channel and input details** pane\. In the **IAM Role** section, the user will choose **Specify custom role ARN** and enter the role name in the field by typing or pasting\. 

An administrator therefore must perform the following setup:
+ Set up all the trusted entity roles that your deployment requires\. See [Creating Trusted Entity Roles](complex-scenario-create-trusted-entity-role.md)\.
+ Set up regular users with restricted permissions for working with roles\. You must also make sure that you have not granted certain permissions; granting those permissions would give the regular users permissions that are too broad for the complex option\. See [Setting Up Permissions for Non\-Administrator Users](complex-scenario-user-permissions.md)\.