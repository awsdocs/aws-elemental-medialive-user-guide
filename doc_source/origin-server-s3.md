# Archive or frame capture output group<a name="origin-server-s3"></a>

Follow this procedure if you [determined](identify-downstream-system.md) that you will create an archive output group or frame capture output group\. The destination for these output groups is always Amazon S3\. 

You and the operator of the downstream system must agree about the destination for the output of this output group\. You will need this information when you [create the MediaLive channel](creating-archive-output-group.md)\.

You must follow this procedure for each output group\.

**To arrange setup of the destination**

1. Decide if you need two destinations for the output: 
   + You need two destinations for output from a [standard channel](plan-redundancy.md)\.
   + You need one destination for output from a single\-pipeline channel\.

1. Consult with the Amazon S3 user and decide on the bucket name or names\. Ask the Amazon S3 user to create any buckets that don't already exist\. 

1. Discuss ownership with the Amazon S3 user\. If the bucket belongs to another AWS account, you typically want that account to become the owner of the output\. For more information, see [Controlling access to the output](#setting-dss-archive-canned-acl), after this procedure\.

1. You can design the full destination paths now, or you can design them when you create the output group\.

   If you want to design the full paths now, but you aren't familiar with the path requirements, see [Fields for the output destination](archive-destinations.md) or [Frame capture destination](framecapture-destinations.md)\.

   If you have two destinations, the destination paths must be different from each other in some way\. At least one of the portions of one path must be different from the other\. It is acceptable for all the portions to be different\. 

1. Make a note of the bucket or the full destination paths\.

Note that you don't need user credentials to send to an S3 bucket\. MediaLive has permission to write to the bucket via the trusted entity\. Someone in your organization should have already set up these permissions\. For more information, see [Reference: summary of requirements for the MediaLive trusted entity](trusted-entity-requirements.md)\.

## Controlling access to the output<a name="setting-dss-archive-canned-acl"></a>

You might be sending output files to an Amazon S3 bucket that is owned by another AWS account\. In this situation, you typically want the other account to become the owner of the output files \(the object being put in the bucket\)\. If the bucket owner doesn't become the object owner, you \(MediaLive\) will be the only agent that can delete the files when the files are no longer required\.

It is therefore in everyone's interest to transfer ownership of the output files after they are in the Amazon S3 bucket\.

To transfer object ownership, the following setup is required:
+ The bucket owner must add a bucket permissions policy that grants you permission to add an Amazon S3 canned access control list \(ACL\) when MediaLive delivers the output files to the bucket\. The bucket owner should read the information in [Managing access with ACLs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/acls) in the Amazon Simple Storage Service user guide\. The bucket owner must set up ACL permissions for the bucket, not for the objects\. 
+ The bucket owner should also set up object ownership\. This feature effectively makes it mandatory \(rather than optional\) for the sender \(MediaLive\) to include the *Bucket owner full control* ACL\. The bucket owner should read the information in [Controlling object ownership](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership) in the Amazon Simple Storage Service user guide\.

  If the bucket owner implements this feature, then you must set up MediaLive to include the ACL\. If you don't, delivery to the Amazon S3 bucket will fail\.
+ You must set up MediaLive to include the *Bucket owner full control** *ACL when it delivers to the bucket\. You will perform this setup when you [create the channel](archive-destinations.md)\.

The S3 canned ACL feature supports ACLs other than *Bucket owner full control*\. But those other ACLs are typically not applicable to the use case of delivering video from MediaLive\.