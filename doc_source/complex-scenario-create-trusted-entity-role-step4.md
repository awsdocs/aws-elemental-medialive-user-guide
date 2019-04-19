# Step 4: Revise the Trust Relationship<a name="complex-scenario-create-trusted-entity-role-step4"></a>

Any person who is an administrator can perform this procedure\. 

When you created the role and established the trusted relationship, you chose EC2 as the service\. You must now modify the role so that the trusted relationship is between your AWS account and MediaLive\.

**To change the trust relationship to MediaLive**

1. On the **Summary** page for the role \(which should still be displayed\), choose **Trust relationships**\.

1. Choose **Edit trust relationship**\.

1. For **Edit Trust Relationship**, for **Policy Document**, change `ec2.amazonaws.com` to `medialive.amazonaws.com`\. 

   The policy document should now look like this: 

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

1. Choose **Update Trust Policy**\.

1. On the **Summary** page, make a note of the value in **Role ARN**\. It looks like this:

   `arn:aws:iam::111122223333:role/MediaLiveAccessRole`

   In the example, `111122223333` is your AWS account number\. 

1. Make a list of all the role ARNs, and include a description of the workflow and users for each\. You will need this list in [Step 6: Setting Up Required Data](setup-user-step-6.md)\.