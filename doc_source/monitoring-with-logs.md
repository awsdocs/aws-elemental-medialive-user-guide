# Monitoring Using Amazon CloudWatch Logs<a name="monitoring-with-logs"></a>

MediaLive produces channel logs that contain detailed information about activity in a channel\. The logs provide a sequential description of activity that occurs in the channel\. These logs can be useful when the information in alerts \([Monitoring a Channel Using Amazon CloudWatch Events](monitoring-via-cloudwatch.md)\) does not provide enough information to resolve an issue on the channel\. 

Channel logs are sent to Amazon CloudWatch Logs\. You can use the standard features of CloudWatch Logs to view and manage the logs\. For more information, see [Amazon CloudWatch Logs User Guide](https://docs.aws.amazon.com//AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html)\.

You should not automate any processing based on the wording in logs because that wording is subject to change\. \(By comparison, you can automate based on the wording in alerts, which are accessed using CloudWatch Events, because the wording of alerts does not change\.\) 

There is a cost for channel logging\. Logging of MediaLive channel activity forms part of your charges for Amazon CloudWatch Logs\. See [Amazon CloudWatch Pricing](https://aws.amazon.com/cloudwatch/pricing/)\. 

**Topics**
+ [Enabling Channel Logs](enabling-disabling-logs.md)
+ [Working with Logs](working-with-logs.md)