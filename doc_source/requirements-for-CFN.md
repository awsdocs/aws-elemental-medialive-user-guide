# Requirements for AWS CloudFormation<a name="requirements-for-CFN"></a>

MediaLive includes a workflow wizard\. Creation of a workflow always includes automatic creation of an AWS CloudFormation stack\. Therefore, to use the workflow wizard, users need permissions in AWS CloudFormation\.


| Permissions | Service name in IAM | Actions | 
| --- | --- | --- | 
| Work with the workflow wizard | AWS CloudFormation |  `ListStacks` `DescribeStacks` `DescribeStackResources` `CreateStack` `DeleteStack`  | 