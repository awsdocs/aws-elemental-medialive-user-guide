# Logging MediaLive API Calls with AWS CloudTrail<a name="logging-using-cloudtrail"></a>

AWS Elemental MediaLive is integrated with AWS CloudTrail, a service that provides a record of actions taken by a user, role, or an AWS service in MediaLive\. CloudTrail captures all API calls for MediaLive as events\. The calls captured include calls from the MediaLive console and code calls to the MediaLive API operations\. If you create a trail, you can enable continuous delivery of CloudTrail events to an Amazon S3 bucket, including events for MediaLive\. If you don't configure a trail, you can still view the most recent events in the CloudTrail console in **Event history**\. Using the information collected by CloudTrail, you can determine the request that was made to MediaLive, the IP address from which the request was made, who made the request, when it was made, and additional details\. 

To learn more about CloudTrail, see the [AWS CloudTrail User Guide](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/)\.

## MediaLive Information in CloudTrail<a name="medialive-info-in-cloudtrail"></a>

CloudTrail is enabled on your AWS account when you create the account\. When activity occurs in MediaLive, that activity is recorded in a CloudTrail event along with other AWS service events in **Event history**\. You can view, search, and download recent events in your AWS account\. For more information, see [Viewing Events with CloudTrail Event History](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html)\. 

For an ongoing record of events in your AWS account, including events for MediaLive, create a trail\. A *trail* enables CloudTrail to deliver log files to an Amazon S3 bucket\. By default, when you create a trail in the console, the trail applies to all AWS Regions\. The trail logs events from all Regions in the AWS partition and delivers the log files to the Amazon S3 bucket that you specify\. Additionally, you can configure other AWS services to further analyze and act upon the event data collected in CloudTrail logs\. For more information, see the following: 
+ [Overview for Creating a Trail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-create-and-update-a-trail.html)
+ [CloudTrail Supported Services and Integrations](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-aws-service-specific-topics.html#cloudtrail-aws-service-specific-topics-integrations)
+ [Configuring Amazon SNS Notifications for CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/getting_notifications_top_level.html)
+ [Receiving CloudTrail Log Files from Multiple Regions](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/receive-cloudtrail-log-files-from-multiple-regions.html) and [Receiving CloudTrail Log Files from Multiple Accounts](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-receive-logs-from-multiple-accounts.html)

All MediaLive actions are logged by CloudTrail and are documented in the https://docs\.aws\.amazon\.com/medialive/latest/apireference/\. 

Every event or log entry contains information about who generated the request\. The identity information helps you determine the following: 
+ Whether the request was made with root or AWS Identity and Access Management \(IAM\) user credentials\.
+ Whether the request was made with temporary security credentials for a role or federated user\.
+ Whether the request was made by another AWS service\.

For more information, see the [CloudTrail userIdentity Element](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference-user-identity.html)\.

## Understanding MediaLive Log File Entries<a name="understanding-medialive-entries"></a>

A trail is a configuration that enables delivery of events as log files to an Amazon S3 bucket that you specify\. CloudTrail log files contain one or more log entries\. An event represents a single request from any source and includes information about the requested action, the date and time of the action, request parameters, and so on\. CloudTrail log files aren't an ordered stack trace of the public API calls, so they don't appear in any specific order\. 

The following example shows a CloudTrail log entry\. The example shows the entry for one API call\. The call is made by the identity that is specified in `userIdentity`, in this case an IAM user with the user name `santosp`\. The call was a `CreateInput` operation coming from the AWS CLI \(as specified in `userAgent`\) running on a computer with the IP address 203\.0\.113\.33:

```
    {
   “eventVersion”: “1.05",
   “userIdentity”: {
       “type”: “IAMUser”,
       “principalId”: “AIDACKCEVSQ6C2EXAMPLE”,
       “arn”: “arn:aws:iam::111122223333:user/santosp”,
       “accountId”: “111122223333”,
       “accessKeyId”: “AKIAOSFODNN7EXAMPLE”,
       “userName”: “santosp”
   },
   “eventTime”: “2019-01-17T21:21:17Z”,
   “eventSource”: “medialive.amazonaws.com”,
   “eventName”: “CreateInput”,
   “awsRegion”: “us-west-2”,
   “sourceIPAddress”: “203.0.113.33”,
   “userAgent”: “aws-cli/1.16.86 Python/2.7.15 Darwin/17.7.0 botocore/1.12.76”,
   “requestParameters”: {
       “mediaConnectFlows”: [],
       “inputSecurityGroups”: [
           “9999999”
       ],
       “sources”: [],
       “roleArn”: “MediaLiveAccessRole”,
       “requestId”: “1111aaaa-9604-4459-a160-46a28ae166",
       “name”: “live_studio_feed”,
       “type”: “RTP_PUSH”,
       }
   },
   “responseElements”: {
       “input”: {
           “arn”: “arn:aws:medialive:us-west-2:111122223333:input:7780651”,
           “id”: “7780651”,
           “name”: “live_studio_feed”,
           “type”: “RTP_PUSH”,
           “sources”: [],
           “destinations”: [
               {
                   “url”: “rtp://198.51.100.10:1935”,
                   “ip”: “198.51.100.10:1935”,
                   “port”: “1935”
               },
               {
                   “url”: “rtp://192.0.2.131:1935”,
                   “ip”: “192.0.2.131:1935”,
                   “port”: “1935”
               }
           ],
           “mediaConnectFlows”: [],
           “state”: “DETACHED”,
           “attachedChannels”: [],
           “securityGroups”: [
               “9999999”
           ],
           “roleArn”: “”
       }
   },
   “requestID”: “d2f882ac-1a9d-11e9-a0e5-afe6a8c88993”,
   “eventID”: “ebbe0290-7a1b-4053-a219-367404e0fe96”,
   “readOnly”: false,
   “eventType”: “AwsApiCall”,
   “recipientAccountId”: “111122223333"
}
```