# Submitting a batch update schedule command<a name="submitting-batch-command"></a>

The command for a batch update schedule command is identical for creating actions, deleting actions, or submitting a combination of create and delete actions\. The command is identical\. Only the contents of the JSON payload differ\.

There are different ways to enter the command to create an action\. We recommend that you follow this usage:
+ Enter the command with two parameters: `channel-id` and `--cli-input-json`\. In this case, you create a file that repeats the channel ID and includes the JSON payload\. 

The instructions and examples in this section illustrate this usage\. 

The following general rules apply to batch update commands:
+ You can create actions when the channel is running or when it is idle\. 
+ You can create any number of actions in one request, or any combination of types of actions in one request\. For example, you can mix the creation of SCTE\-35 message actions and image overlay actions\. 
+ If you create several actions in one request and one of the create requests fails \(usually because the start time isn't sufficiently in the future\), then they all fail\.

The following rules apply to delete actions:
+ You can delete an action when the channel is running or when it is idle\. 
+ You can delete any number of actions in one request, or any combination of types of actions in one request\. For example, you can mix the deletion of SCTE\-35 message actions and image overlay actions\. 
+ If you delete several actions in one request and one of the delete requests fails \(usually because the start time isn't sufficiently in the future\), then they all fail\.

**To submit a batch command**

1. Before you add or delete actions, read [Creating actions in the schedule \(console\)](schedule-using-console-create.md) and [Deleting actions from the schedule \(console\)](schedule-using-console-delete.md)\.

1. Prepare a file that contains the channel ID and the appropriate JSON payload for the actions\. For the structure and examples of the JSON payload for different actions, see the sections that follow\. 

1. Give the file a suitable name with a `.txt` extension\. For example, the file name for a payload that creates only actions might be `schedule-create-actions.txt`\. 

1. Save the file to the folder where you are running the AWS CLI\.

1. On the command line, enter this command:

   `aws medialive batch-update-schedule --channel-id value --cli-input-json value`
   + In the value for `--channel-id`, enter the channel ID as a number\.
   + In the value for `--cli-input-json`, enter the file name in this format:

     `file://filename.txt`

   For example: 

   `aws medialive batch-update-schedule --channel-id 999999 --cli-input-json schedule-create-actions.txt`

1. To submit the command, press **Enter**\. The response appears on the screen\. The response repeats the data from the request\.