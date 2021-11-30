# Requirements for AWS Elemental MediaStore<a name="requirements-for-mediastore"></a>

Your deployment might include using files in an AWS Elemental MediaStore container\. For example, your deployment might use files in the following ways:
+ As the source for an HLS input
+ As the destination for an HLS output group

The user needs permissions to perform actions in MediaStore when they use the MediaLive workflow wizard\. The user doesn't need special permissions when they use the regular MediaLive console to specify a MediaStore container in a channel\. 


| Permissions | Service name in IAM | Actions | 
| --- | --- | --- | 
| Use the workflow wizard to create a MediaStore container, if your organization supports MediaStore as an output destination\.Use the workflow wizard, to delete a workflow that includes a MediaStore output\. | MediaStore | List\*`Describe*``Create*``Delete*` | 