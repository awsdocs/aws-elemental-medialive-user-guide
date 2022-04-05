# Data protection in AWS Elemental MediaLive<a name="data-retention"></a>

The AWS [shared responsibility model](http://aws.amazon.com/compliance/shared-responsibility-model/) applies to data protection in AWS Elemental MediaLive\. As described in this model, AWS is responsible for protecting the global infrastructure that runs all of the AWS Cloud\. You are responsible for maintaining control over your content that is hosted on this infrastructure\. This content includes the security configuration and management tasks for the AWS services that you use\. For more information about data privacy, see the [Data Privacy FAQ](http://aws.amazon.com/compliance/data-privacy-faq)\. For information about data protection in Europe, see the [AWS Shared Responsibility Model and GDPR](http://aws.amazon.com/blogs/security/the-aws-shared-responsibility-model-and-gdpr/) blog post on the *AWS Security Blog*\.

For data protection purposes, we recommend that you protect AWS account credentials and set up individual user accounts with AWS Identity and Access Management \(IAM\)\. That way each user is given only the permissions necessary to fulfill their job duties\. We also recommend that you secure your data in the following ways:
+ Use multi\-factor authentication \(MFA\) with each account\.
+ Use SSL/TLS to communicate with AWS resources\. We recommend TLS 1\.2 or later\.
+ Set up API and user activity logging with AWS CloudTrail\.
+ Use AWS encryption solutions, along with all default security controls within AWS services\.
+ Use advanced managed security services such as Amazon Macie, which assists in discovering and securing personal data that is stored in Amazon S3\.
+ If you require FIPS 140\-2 validated cryptographic modules when accessing AWS through a command line interface or an API, use a FIPS endpoint\. For more information about the available FIPS endpoints, see [Federal Information Processing Standard \(FIPS\) 140\-2](http://aws.amazon.com/compliance/fips/)\.

We strongly recommend that you never put confidential or sensitive information, such as your customers' email addresses, into tags or free\-form fields such as a **Name** field\. This includes when you work with AWS Elemental MediaLive or other AWS services using the console, API, AWS CLI, or AWS SDKs\. Any data that you enter into tags or free\-form fields used for names may be used for billing or diagnostic logs\.

 If you provide a URL to an external server, MediaLive requires that you do not include credentials information in the URL to validate your request to that server\. If a URL to an external server requires credentials, we recommend you use the Parameter Store feature in AWS Systems Manager\. For more information, and the steps to implement AWS Systems Manager Parameter Store, see [Requirements for AWS Systems Manager—creating password parameters in Parameter Store](https://docs.aws.amazon.com/medialive/latest/ug/requirements-for-EC2.html)\.

AWS Elemental MediaLive doesn't require that you supply any customer data\. There are no fields in channels, devices, inputs, input security groups, multiplexes, or reservations, where there is an expectation that you will provide customer data\. 

MediaLive includes features such as the AWS Systems Manager Parameter Store that provide you with a secure way to handle sensitive information\. You should always use these features to pass a password; you should not circumvent them by including a password in a URL\.

## Deleting data in AWS Elemental MediaLive<a name="data-retention-deleting-data"></a>

You can delete data from AWS Elemental MediaLive by deleting the object, for example, the channel or input\. You can delete data using the console, REST API, AWS CLI, or AWS SDKs\. The data will be deleted; no further steps are required after you delete data by completing a delete operation\.

To delete data using the console, see the following sections:
+ [Deleting a channel](editing-deleting-channel.md#deleting-a-channel)
+ [Working with MediaLive devices](eml-devices.md)
+ [Deleting an input](delete-input.md)
+ [Deleting an input security group](delete-input-security-group.md)
+ [ Deleting multiplexes, programs, and channels ](delete-multiplex-program.md)
+ [Deleting a reservation](deleting-reservations.md)