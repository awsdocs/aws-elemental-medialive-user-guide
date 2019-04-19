# Data Retention and Personally Identifiable Information<a name="data-retention"></a>

AWS Elemental MediaLive doesn't require that you supply any customer data\. There are no fields in channels, inputs, or input security groups where there is an expectation that you will provide customer data\. 

Don't put sensitive identifying information such as customer account numbers into free\-form fields such as a **Name** field\. This includes when you work with MediaLive using the console, REST API, AWS CLI, or AWS SDKs\. Any given piece of data that you enter into MediaLive might get picked up for inclusion in diagnostic logs\.

When you provide a URL to an external server, don't include credentials information in the URL to validate your request to that server\. MediaLive includes features such as the Amazon EC2 Systems Manager Parameter Store that provide you with a secure way to handle sensitive information\. You should always use these features to pass a password; you should not circumvent them by including a password in a URL\.

## Deleting Data in AWS Elemental MediaLive<a name="data-retention-deleting-data"></a>

You can delete data from AWS Elemental MediaLive by deleting the object, for example, the channel or input\. You can delete data using the console, REST API, AWS CLI, or AWS SDKs\. The data will be deleted; no further steps are required after you delete data by completing a delete operation\.

To delete data using the console, see the following sections:
+ [Deleting a Channel](editing-deleting-channel.md#deleting-a-channel)
+ [Deleting an Input](delete-input.md)
+ [Deleting an Input Security Group](delete-input-security-group.md)