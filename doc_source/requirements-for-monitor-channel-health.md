# Requirements for Amazon CloudWatch—Monitoring Channel Health<a name="requirements-for-monitor-channel-health"></a>

The AWS Elemental MediaLive console includes a page \(**Channel details**\) that collects CloudWatch metrics information about the health of channels and displays it directly on the MediaLive console\. 

You must decide if you want to give some or all of your users permission to view metrics on the console\.

For a user to view this information on the MediaLive console, that user must have view permissions for metrics operations in Amazon CloudWatch\. When users have these permissions, they can also view the information through the CloudWatch console, AWS CLI, or REST API\.

The following table shows the actions in IAM that relate to access for monitoring channel health\.


| Permissions | Service Name in IAM | Actions | 
| --- | --- | --- | 
| View Metrics  | CloudWatch | ListMetrics`GetMetricData``GetMetricStatistics` | 