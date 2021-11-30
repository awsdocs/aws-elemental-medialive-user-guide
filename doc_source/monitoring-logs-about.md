# About channel logs<a name="monitoring-logs-about"></a>

MediaLive produces channel logs that contain detailed information about activity in a channel\. The logs provide a sequential description of activity that occurs in the channel\. These logs can be useful when the information in alerts \([Monitoring a channel or multiplex using Amazon CloudWatch Events](monitoring-via-cloudwatch.md)\) does not provide enough information to resolve an issue on the channel\. 

There are two sets of channel logs:
+ Channel encoder logs\. You must [enable ](enabling-disabling-logs.md)these logs\.
+ Channel as\-run logs\. MediaLive always produces these logs\.

## Comparison of types of logs<a name="monitoring-logs-comparison"></a>

**Features that are the same in both types of logs**  
Both types of logs are sent to Amazon CloudWatch Logs\. You can use the standard features of CloudWatch Logs to view and manage the logs\. For more information, see [Amazon CloudWatch Logs User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html)\.

**Features that are different in the two types of logs**  
The following table describes the differences between channel encoder logs and channel as\-run logs\.


|  | Encoder logs | As\-run logs | 
| --- | --- | --- | 
| Trigger for creation | You must [enable these logs ](enabling-disabling-logs.md)in order for MediaLive to produce them\. | MediaLive always produces these logs\. | 
| Level of detail | You can set a logging level to control the detail collected\. | You can't change the logging level\. | 
| Cost | There is a cost for these logs, as part of your charges for Amazon CloudWatch Logs\. See [Amazon CloudWatch Pricing](https://aws.amazon.com/cloudwatch/pricing/)\. Remember to [remove the logs](working-with-logs.md#manage-log-storage) after you delete the channel\. | These logs are free\. | 
| CloudWatch log stream | The log stream is named after the ARN/pipeline\.  | The log stream is named after the ARN/pipeline with \_as\_run appended to the name\. | 
| Automation | You should not automate any processing based on the wording in these logs because that wording is subject to change\.\(By comparison, you can automate based on the wording in alerts, which are accessed using CloudWatch Events, because the wording of alerts does not change\.\)  | You can automate based on the wording in these logs\. | 