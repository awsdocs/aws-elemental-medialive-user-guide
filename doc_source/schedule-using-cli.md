# Working with the schedule \(AWS CLI\)<a name="schedule-using-cli"></a>

You can use the AWS CLI to work with the schedule programmatically\. The sections later in this chapter describe how to enter the appropriate commands\. These sections assume that you are familiar with the basics of using the AWS CLI\. For information about the basics, see the [AWS CLI Command Reference](https://docs.aws.amazon.com/cli/latest/reference/)\. 

The following sections describe each command and provide this additional information:
+ A description of the AWS CLI command syntax\.
+ A description of the schema for the request or response JSON payload\. This payload is shown using the syntax for the AWS CLI\. 
+ An example of the request or response JSON payload\. This payload is also shown using the syntax for the AWS CLI\.

For details on the JSON contents, we recommend that you read the [AWS Elemental MediaLive API Reference](https://docs.aws.amazon.com/medialive/latest/apireference/)\. This guide is easy to use because it includes links from elements in the JSON payload to tables that describe the element\. But you must adjust the syntax of the elements in the JSON code because the AWS CLI uses one form of capitalization for elements \(for example, `SubSegmentNum`\) and the API uses another form \(for example, `subSegmentNum`\)\. 

**Topics**
+ [Creating and deleting using a batch command](about-batch-update-schedule.md)
+ [Submitting a batch update schedule command](submitting-batch-command.md)
+ [JSON payload for create actions](schedule-create-json.md)
+ [JSON payload for delete actions](cli-schedule-delete-json.md)
+ [JSON payload for combining create and delete](schedule-create-and-delete-json.md)
+ [Viewing the schedule \(AWS CLI\)](viewing-schedule-using-cli.md)