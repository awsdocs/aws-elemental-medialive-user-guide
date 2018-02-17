# Set up Permissions for AWS Elemental MediaLive<a name="permissions-medialive"></a>

AWS Elemental MediaLive needs permission to make calls to the APIs of Amazon EC2 Systems Manager Parameter Store, Amazon S3 \(if you plan to store and/or retrieve assets on this service\) and AWS Elemental MediaStore \(if you plan to store and/or retrieve assets on this service\)\. You set this permission as follows:

+ You create a role called MediaLiveAccessRole and associate one policy with that role\.

+ You create a second policy that gives access to more services, then associate that policy with the role\.

+ You modify the trust relationship between your AWS account and the AWS Elemental MediaLive service\. 

## Step 1: Create a Role for the Service<a name="permissions-medialive-step1"></a>

You must create a role for AWS Elemental MediaLive\. The role sets up a trusted relationship between your AWS account and AWS Elemental MediaLive\.

1. Open the IAM console\.

1. In the navigation pane, choose Roles\.

1. On the Role page, choose Create role\.

1. In the Create role page, in Select type of trusted entity, choose AWS service as the type \(the default\)\.

1. In Choose the service that will use this role, choose EC2\.

   You are choosing EC2 because AWS Elemental MediaLive is not currently included in this list\. Choosing EC2 lets you create a role; in a later step you will change this role to mention AWS Elemental MediaLive instead of EC2\.

1.  In Select your use case, choose EC2\. \(Again, you will later change this service to AWS Elemental MediaLive\.\)

1. Choose Next: Permissions in order to create a policy for this role\.

1. Choose AmazonSSMReadOnlyAccess and choose Next: Review\.

1. In Role name, type a name\. We strongly recommend using the name “MediaLiveAccessRole”\.

1. Look at the other fields: Amazon EC2 is a trusted entity and the policy attached to this role is AmazonSSMReadOnlyAccess

1. Choose Create role\.

## Step 2: Modify the Policy<a name="permissions-medialive-step2"></a>

You attached a policy that gives access to AmazonSSMReadOnlyAccess\. “SSM” refers to the Amazon EC2 Systems Manager Parameter Store\. You must now create a second policy to give access to Amazon S3 and AWS Elemental MediaStore,:

1. From the Role list, choose the role you just created\.

1. On Summary, choose Add inline policy\.

1. On Set permissions, choose Custom Policy and choose Select\.

1. On Review policy, in Policy name, type a suitable name such as S3andMediaStoreReadWriteAccess\. 

1. In Policy document, paste the following:

   ```
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Action": [
           "s3:ListBucket",
           "s3:PutObject",
           "s3:GetObject",
           "s3:DeleteObject"
           ],
         "Resource": "*"
       },
       {
         "Effect": "Allow",
         "Action": [
         "mediastore:ListContainer",
         "mediastore:DescribeObject",
         "mediastore:PutObject",
         "mediastore:GetObject",
         "mediastore:DeleteObject"
           ],
         "Resource": "*"
       }
     ]
   }
   ```

   These lines allow AWS Elemental MediaLive to access Amazon S3 and AWS Elemental MediaStore\.

1. Choose Validate Policy, then choose Apply Policy\.

1. In the Summary page, you can see that the role MediaLiveAccessRole now has two policies: AmazonSSMReadOnlyAccess and S3AndMediaStoreReadWriteAccess\. Both policies apply equally to this role\.

## Step 3: Revise the Trust Relationship<a name="permissions-medialive-step3"></a>

When you created the role and established the trusted relationship, you chose EC2 as the service\. You must now modify the role so that the trusted relationship is between your AWS account and AWS Elemental MediaLive\.

1. In the Summary page for MediaLiveAccessRole \(which should still be displayed\), choose Trust relationships\.

1. Choose Edit trust relationship\.

1. In Edit Trust Relationship, in Policy Document, look at the text that is currently there\. It mentions EC2\.

1. In Policy Document, paste the following in order to change the policy to mention AWS Elemental MediaLive instead of EC2:

   ```
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Principal": {
         "Service": "medialive.amazonaws.com"
         },
         "Action": "sts:AssumeRole"
       }
     ]
   }
   ```

1. Choose Update Trust Policy\.

1. On the Summary page, make a note of the value in Role ARN\. It looks like this:

   arn:aws:iam::111122223333:role/MediaLiveAccessRole, where 111122223333 is your AWS account number\. 

   You will use this Role ARN when using AWS Elemental MediaLive, so either make a note of it now, or be prepared to come back to this page to obtain it as required\. 