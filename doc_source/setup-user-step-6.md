# Step 6: Setting Up Required Data<a name="setup-user-step-6"></a>

After you set up users with the appropriate access, you or another administrator should provide users with the information that they need to use MediaLive:
+ Provide each user with a list of the MediaLive operations that they have access to\. To prevent user frustration, make sure that users know which console pages they can't display\. Make sure to include information about the channel metrics that users can't display on the **Channel details** page\.
+ If some external servers require user credentials, and only one or two users or administrators are responsible for creating password parameters in the AWS Systems Manager Parameter Store, make sure that those users are aware of their responsibility\. 

  Also make sure that those users provide other users with the password parameters that those other users need\. 
+ If a user or administrator is responsible for setting up other users for email notification, let that user know\. Or if each user is responsible for setting up their own email notification, let each user know\. Users can read [Monitoring a Channel Using Amazon CloudWatch Events](monitoring-via-cloudwatch.md) for instructions\.
+ For the MediaLive role, if you chose the [simple option](scenarios-for-medialive-role.md#about-simple-scenario), make sure users know that the only role they will ever choose is the `MediaLiveAccessRole`\.

  If you set up for the[ complex option](scenarios-for-medialive-role.md#about-complex-scenarios), let the user or administrator who must create roles know that they must give other users a list of the roles \(the list of role ARNs\) that each user can use\. 