# Step 1: Determine the access requirements<a name="complex-scenario-create-trusted-entity-role-step1"></a>

This requirements analysis must be performed by a person in your organization who understands your organization's requirements for access to resources\. This person must understand whether there is a requirement that MediaLive channels should be restricted in their access to resources in other AWS services\. For example, this person should determine whether channels should be restricted in their access to containers in MediaStore so that a specified channel can access some containers and not others\.

You must identify the services that MediaLive will interact with in your deployment\. Then within each service, you must identify the operations and resources that MediaLive needs access to\.

**To determine the access requirements for MediaLive**

1. See the table in [Reference: summary of requirements for the MediaLive trusted entity](trusted-entity-requirements.md) for information about the services that MediaLive typically needs access to\. Determine which of those services your deployment uses and which operations it needs\.

1. Within a service, determine the number of policies that you need to create\. Do you need several different combinations of objects and operations for different workflows, and do you need to keep those combinations separate from each for security reasons? 

   Specifically, determine whether you need access to different resources for different workflows, and whether it's important to restrict access to specific resources\. For example, in AWS Systems Manager Parameter Store you might have passwords that belong to different workflows, and you might want to allow only specific users to access the passwords for any given workflow\.

   If different workflows have different requirements for objects, operations, and resources, then for that service you need separate policies for each workflow\. 

   After you perform this analysis, you might determine that you need three different policies for MediaStore, four different policies for Amazon S3, and three policies for AWS Systems Manager Parameter Store\. 

1. Design each policy: identify the allowed \(or not allowed\) objects, operations, and the allowed \(or not allowed\) resources in the policy\. 

1. Determine if any of the policies that you have identified are covered by a managed policy\. 

1. For each workflow, identify the policies that you need for all the services that the workflow uses\.

   For example, for one workflow, you might need policy X for MediaStore, policy A for Amazon S3, and policy 1 for AWS Systems Manager Parameter Store\. For the second workflow, you might need policy Y for MediaStore, policy B for Amazon S3, and policy 1 for AWS Systems Manager Parameter Store\. For the third workflow, you need the same policies as for the first workflow\. 

1. Identify the number of roles that you need\. You need one role for each unique combination of policies\. Following our example, you need two roles: one role for the first and third workflows, and another for the second workflow\.

1. Assign names to all the policies and roles that you have identified\. Take care not to include sensitive identifying information \(such as a customer account name\) in these names\. 