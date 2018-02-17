# Handling AWS Elemental MediaLive Alerts<a name="setting-up-alerts"></a>

AWS Elemental MediaLive provides feedback to you on the status of channels\. It does this by creating Amazon CloudWatch events that hold alert information\. You can manage these events using Amazon CloudWatch event rules and deliver them in emails or SMS messages\. You can deliver events to a number of destinations; this chapter describes how to deliver them via the Amazon Simple Notification Service \(SNS\)\.

For complete information about the options for managing events using Amazon CloudWatch, see [the Cloudwatch User Guide](http://docs.aws.amazon.com//AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html)\.

For complete information about using SNS, see [the SNS Developer Guide](http://docs.aws.amazon.com//sns/latest/dg/welcome.html)\.