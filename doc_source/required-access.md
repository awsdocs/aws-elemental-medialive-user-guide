# Required Permissions in AWS Elemental MediaLive<a name="required-access"></a>

There are several identities that must have permissions to work with AWS Elemental MediaLive\.

+ Any person who is using the console, the CLI, or the REST API \(via a REST client application\) must have the appropriate permissions on the desired operations of AWS Elemental MediaLive\. This access is conferred by setting up people as IAM users\.

+ Any software application that is using the REST API or an SDK must have the appropriate permissions on the desired operations of AWS Elemental MediaLive\. One way to confer this access is by setting up software applications as IAM users\.

+ AWS Elemental MediaLive itself must be an IAM trusted entity in order to make calls to the APIs of Amazon EC2 Systems Manager Parameter Store, Amazon S3 \(if you plan to store and/or retrieve assets on this service\) and AWS Elemental MediaStore \(if you plan to store and/or retrieve assets on this service\)\. It is extremely likely that AWS Elemental MediaLive will need to be set up in this way\.

+ The person who sets up AWS Elemental MediaLive as a trusted entity needs read/write access with Amazon IAM\. See [[ERROR] BAD/MISSING LINK TEXT](permissions-medialive.md)\.