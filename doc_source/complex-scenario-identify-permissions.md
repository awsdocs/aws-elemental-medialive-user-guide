# Identifying Permissions<a name="complex-scenario-identify-permissions"></a>

With the complex option, regular users don't create trusted entity roles\. But they will attach existing roles to the channels that they create by completing the **IAM Role** section in the **Channel and input details** pane\.

To work with this section, regular users therefore must have access to specific IAM actions\. 

The following screenshot shows the **IAM Role** section on the **Channel and input details** pane as it appears when you start to create a channel\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/medialiveaccessrole_complex.png)

You must set up permissions for regular users so that they can access only specific fields on the **IAM Role** section in the **Channel and input details** pane\. Typically, you must set up as follows:
+ Users must *not* be able to choose the selection field that accompanies the **Use existing role** field\. You probably want to disable this selection field because you don't want users to choose a role from the list that accompanies this field\. If this field is enabled for a user, that user can view all the roles that are created in the account, which would defeat the requirement to restrict access so that users can view and attach only specific roles\. 
+ Users must *not* be able to choose the **Create role from template** field\. Regular users do not create roles\. 
+ Users must be able to enter values into the entry field that accompanies the **Specify custom role ARN** field\. When this entry field is enabled, the user can enter or paste one of the role names that you provide\.
+ Users do *not* need to be able to choose the **Update** button because this button only ever appears in implementations that use the `MediaLiveAccessRole`\. The complex option does not use this role; therefore, this button never appears\.

To ensure that users interact with this section of the console in this restricted way, you must grant access to only one IAM action, as shown in the following table\.


| Permissions | Service Name in IAM | Actions | 
| --- | --- | --- | 
| Attach  | IAM |  `iam:PassRole`  | 

Equally important, you must make sure that you do *not* grant access to the following actions:
+ `iam:ListRole`
+ `iam:CreateRole`
+ `iam:PutRolePolicy`
+ `iam:AttachRolePolicy`