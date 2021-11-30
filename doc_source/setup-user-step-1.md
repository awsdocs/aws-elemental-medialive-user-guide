# Step 1: Identify requirements for permissions for users<a name="setup-user-step-1"></a>

You must identify the IAM permissions that you need to grant to users, for AWS Elemental MediaLive features and for ancillary services that MediaLive always interacts with\. 

To do that, you should understand the MediaLive workflows for your organization and the different AWS services that the workflows use\.

You might not want all regular users to have the same permissions\. For example, you might be able to group regular users into three sets: users who can start channels and watch channel activity, users who have some write capabilities, and advanced users who can do everything\. As you identify these permissions, think about how many different sets of users you need\. 

**Topics**
+ [Requirements for AWS Elemental MediaLive features](requirements-for-medialive.md)
+ [Requirements for AWS CloudFormation](requirements-for-CFN.md)
+ [Requirements for Amazon CloudFront](requirements-for-CFront.md)
+ [Requirements for AWS CloudTrail](requirements-for-cloudtrail.md)
+ [Requirements for Amazon CloudWatch—monitoring channel health](requirements-for-monitor-channel-health.md)
+ [Requirements for CloudWatch and Amazon SNS—setting up email notification](requirements-for-email-notification.md)
+ [Requirements for Amazon CloudWatch Logs—setting up channel logging](requirements-for-console-logging.md)
+ [Requirements for Amazon Elastic Compute Cloud—VPC inputs](requirements-for-vpc-input.md)
+ [Requirements for Amazon Elastic Compute Cloud—delivery via VPC](requirements-vpc-delivery.md)
+ [Requirements for AWS Identity and Access Management—trusted entity role](requirements-for-medialiverole.md)
+ [Requirements for AWS Elemental MediaConnect](requirements-for-media-connect.md)
+ [Requirements for AWS Elemental MediaPackage](requirements-for-mediapackage.md)
+ [Requirements for AWS Elemental MediaStore](requirements-for-mediastore.md)
+ [Requirements for AWS Resource Groups—tagging](requirements-for-tagging.md)
+ [Requirements for Amazon S3](requirements-for-s3.md)
+ [Requirements for AWS Systems Manager—creating password parameters in parameter store](requirements-for-EC2.md)