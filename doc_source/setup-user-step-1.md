# Step 1: Identify Requirements for Permissions for Users<a name="setup-user-step-1"></a>

You must identify the IAM permissions that you need to grant to users, for AWS Elemental MediaLive features and for ancillary services that MediaLive always interacts with\. 

To do that, you should understand the MediaLive workflows for your organization and the different AWS services that the workflows use\.

You might not want all regular users to have the same permissions\. For example, you might be able to group regular users into three sets: users who can start channels and watch channel activity, users who have some write capabilities, and advanced users who can do everything\. As you identify these permissions, think about how many different sets of users you need\. 

**Topics**
+ [Requirements for AWS Elemental MediaLive Features](requirements-for-medialive.md)
+ [Requirements for AWS CloudTrail](requirements-for-cloudtrail.md)
+ [Requirements for Amazon CloudWatch—Monitoring Channel Health](requirements-for-monitor-channel-health.md)
+ [Requirements for CloudWatch and Amazon SNS—Setting Up Email Notification](requirements-for-email-notification.md)
+ [Requirements for Amazon CloudWatch Logs—Setting Up Channel Logging](requirements-for-console-logging.md)
+ [Requirements for Amazon Elastic Compute Cloud—VPC Inputs](requirements-for-vpc-input.md)
+ [Requirements for AWS Identity and Access Management—Trusted Entity Role](requirements-for-medialiverole.md)
+ [Requirements for AWS Elemental MediaConnect](requirements-for-media-connect.md)
+ [Requirements for AWS Elemental MediaPackage](requirements-for-mediapackage.md)
+ [Requirements for AWS Elemental MediaStore](requirements-for-mediastore.md)
+ [Requirements for AWS Resource Groups—Tagging](requirements-for-tagging.md)
+ [Requirements for Amazon S3](requirements-for-s3.md)
+ [Requirements for AWS Systems Manager—Creating Password Parameters in Parameter Store](requirements-for-EC2.md)