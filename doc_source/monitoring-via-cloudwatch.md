# Monitoring a Channel Using Amazon CloudWatch Events<a name="monitoring-via-cloudwatch"></a>

AWS Elemental MediaLive automatically turns alert information into events in CloudWatch Events\. You can use Amazon CloudWatch Events to manage these events\. For example, you can create event rules and deliver the events in emails or SMS messages\. You can deliver events to a number of destinations\. This chapter describes how to deliver them through Amazon Simple Notification Service \(SNS\)\. 

For complete information about the options for managing events using Amazon CloudWatch Events, see the [Cloudwatch Events User Guide](https://docs.aws.amazon.com//AmazonCloudWatch/latest/events/WhatIsCloudWatchEvents.html)\.

For complete information about using Amazon SNS, see the [SNS Developer Guide](https://docs.aws.amazon.com//sns/latest/dg/welcome.html)\.

**Topics**
+ [Option 1: Send all MediaLive Events to an Email Address](option-1.md)
+ [Option 2: Send Events for Specific Channels to an Email Address](option-2.md)