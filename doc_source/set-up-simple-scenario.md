# Requirements for Permissions for the Simple Option<a name="set-up-simple-scenario"></a>

Read this section if you decide that the [simple option](scenarios-for-medialive-role.md#about-simple-scenario) for the trusted entity is appropriate to your deployment\. 

\(To set up for the complex option, see [Setting Up AWS Elemental MediaLive as a Trusted Service](setup-medialive-trusted-service.md)\.\)

For users to work in the **IAM Role** section on the **Channel and input details** pane, they must have access to specific IAM actions\. 

The following screenshot shows the **IAM Role** section on the **Channel and input details** pane as it appears when you start to create a channel\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/medialiveaccessrole_withUpdateButton.png)

You must set up users as follows:
+ Users must be able to choose `MediaLiveAccessRole` from the selection field that accompanies the **Use existing role** field\. 
+ Users must be able to choose the **Create role from template** field\. \(The role needs to be created only once, by the first user to create a channel\. But it is easiest to give all users these permissions\.\) 
+ Users do not need to be able to use the **Specify custom role ARN** field\. They will use `MediaLiveAccessRole`\. They will never use a custom role\.
+ Users must be able to choose the **Update** button, in order to update the `MediaLiveAccessRole` from time to time\. 

The following table shows the service and action in IAM that you must grant to regular users with the simple option\. 


| Permissions | Service Name in IAM | Actions | 
| --- | --- | --- | 
|  Choose the **Create role from template option**  | IAM |  `CreateRole` `PutRolePolicy` `AttachRolePolicy`  | 
|  Choose **MediaLiveAccessRole** from the list in **Use existing role**  | IAM |  `ListRole` `PassRole`   | 
| Choose Update | IAM |  `GetRolePolicy` `PutRolePolicy` `AttachRolePolicy`  | 