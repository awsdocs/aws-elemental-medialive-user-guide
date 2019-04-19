# Requirements for CloudWatch and Amazon SNS—Setting Up Email Notification<a name="requirements-for-email-notification"></a>

MediaLive provides information about channels as they are running\. It sends this information to Amazon CloudWatch as events\. The details of these events can optionally be distributed to one or more users\. Someone must set up this distribution\. \(For the setup procedure, see [Monitoring a Channel Using Amazon CloudWatch Events](monitoring-via-cloudwatch.md)\.\) 

You must decide if you want to give some or all of your users these permissions\. You might choose to allow each user to perform their own distribution setup\. Or you might decide that an administrator must be responsible for performing the setup at startup for applicable users, and then again whenever a new user is added\.

The following table shows the actions in IAM that relate to access for setting up email notification\.


| Permissions | Service Name in IAM | Actions | 
| --- | --- | --- | 
| Write  | CloudWatch Events | All actions | 
| Write | SNS  | All actions | 