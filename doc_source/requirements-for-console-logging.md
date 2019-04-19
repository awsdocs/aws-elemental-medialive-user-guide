# Requirements for Amazon CloudWatch Logs—Setting Up Channel Logging<a name="requirements-for-console-logging"></a>

 MediaLive produces channel logs that it sends to CloudWatch Logs, where users can view them\. For more information about channel logs, see [Monitoring Using Amazon CloudWatch Logs](monitoring-with-logs.md)\. 

You must decide if you want to give some or all of your users permission to view the logs in CloudWatch Logs\.

You must also decide if you want to give some or all of your users permission to set the retention policy for logs\. If you decide not to give this access to any user, an administrator must be responsible for setting the policy\. 

Users don't need special permission to enable logging from within MediaLive\.

The following table shows the actions in IAM that relate to access for setting up channel logs\.


| Permissions | Service Name in IAM | Actions | 
| --- | --- | --- | 
| View Logs  | CloudWatch Logs | FilterLogEvents`GetLogEvents` | 
| Set Retention Policy |  CloudWatch Logs | DeleteRetentionPolicy`PutRetentionPolicy`  | 