# JSON Payload in Different Interfaces<a name="batchupdatecommand-payloads"></a>

The JSON payload for the command is different for the different interfaces:
+ In the AWS CLI, the contents of the payload depend on how you use the command:
  + You can enter a command with two parameters: `channel-id` and `--cli-input-json`\. In this case, you create a file that repeats the channel ID and includes the JSON payload\. 
  + You can enter a command with three parameters: one for the channel ID, one for the JSON payload for the create actions \(if applicable\), and one for the JSON payload for the delete actions \(if applicable\)\. You pass the payloads in the command\. If both parameters are present, each parameter takes a separate payload\. But the two payloads are validated and performed as a batch\. 

  The payload for the AWS CLI is always Pascal case \(upper camel case\)\. 
+ In the API, there is one payload with two sections, a `CREATES` section and a `DELETES` section\. A request can contain one or both sections\. 

  The payload for the API is always camel case for variable names and Pascal case for classes\.
+ In the AWS SDKs, the JSON payload is represented by constructs that are suitable to that SDK language\. 

To get more familiar with individual actions, we recommend that you use the MediaLive console to create an action\. After you create the action, use the [DescribeSchedule](viewing-schedule-using-cli.md) command in the appropriate interface \(for example, the AWS CLI or an SDK\) to obtain the raw JSON payload for the entire schedule\. You can then copy individual actions and save them as models to use when working programmatically\.