# Step 3: Create Roles<a name="complex-scenario-create-trusted-entity-role-step3"></a>

Any person who is an administrator can perform the procedure to create a role and attach policies to the role\. 

In [Step 1: Determine the Access Requirements](complex-scenario-create-trusted-entity-role-step1.md), someone in your organization identified the roles that you need to create\. Create those roles now using IAM\. 

**To create a role and attach a policy to it**

1. Sign into the AWS Management Console as an administrator, and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Roles**\.

1. On the **Role** page, choose **Create role**\.

1. On the **Create role** page, in the **Select type of trusted entity** section, choose **AWS service** \(the default\)\.

1. In **Choose the service that will use this role**, choose **EC2**\. 

   You choose EC2 because MediaLive is not currently included in this list\. Choosing EC2 lets you create a role; in a later step, you will change this role to mention MediaLive instead of EC2\.

1. Choose **Next: Permissions**\.

1. In the **Attach permissions policies** section, select all the policies that apply for this role, and then choose **Next: Tags**\.

1. Add tags if your organization has a policy to create tags for resources\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\. Then choose **Next: Review**\.

1. Choose **Next: Review**\.

1. For **Role name**, enter a name\. We recommend that you don't use the name `MediaLiveAccessRole` because it is reserved for the [simple option](scenarios-for-medialive-role.md#about-simple-scenario)\. Instead, use a name that includes `medialive` and describes this role's purpose\. 

1. For **Trusted entities**, Amazon EC2 \(`ec2.amazonaws.com`\) is displayed as the trusted entity, but you will modify that line in the next procedure\.

1. Choose **Create role**\.