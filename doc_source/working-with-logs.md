# Working with logs<a name="working-with-logs"></a>

You view both encoder logs and as\-run logs on the CloudWatch Logs console, in the same way that you view logs for any service\. 

You don't have to set up the logs, logging groups, or log streams on the CloudWatch Logs console because MediaLive automatically sets them up for you\. 
+ Log group – The log group is always the following: **ElementalMediaLive**\.
+ Log stream –The log stream is named as follows:
  + Encoder logs – named after the ARN/pipeline\. 
  + As\-run logs – named after the ARN/pipeline with `_as_run` appended\.

  For example:

  `arn_aws_medialive_us-west-2_111122223333_channel_5106412_0`

  `arn_aws_medialive_us-west-2_111122223333_channel_5106412_0_as_run`

  Where `5106412` is the channel ID and `0` is the pipeline\.

## Content of encoder logs<a name="content-logs"></a>

The logs are in JSON format:

```
{
    "encoder_pipeline": 0,
    "severity": "I",
    "timestamp": "2018-05-21T16:36:41.650318",
    "channel_arn": "arn:aws:medialive:us-west-2:111122223333:channel:5106412",
    "logger_name": "",
    "message": "Probing input media..."
  },  
.
.
.
]
```

The data is the following:
+ `encoder_pipeline`: `0` or `1` \(if the channel is set up as a [standard channel](channel-class.md) and therefore has two pipelines\)\.
+ `severity`: A letter\. The logging level \(which you set when you enable logging\) controls which severities could appear in logs\. For more information, see [Log Levels and Verbosities](#log-levels)\.
+ `timestamp`: The time in ISO 8601 format: yyyy \- mm \- dd T hh : mm : ss : decimal fraction of second\.
+ `channel_arn`: The ARN plus the channel ID\. In the preceding example, the channel has ID `5106412`\.
+ `logger_name`: This might be blank or might specify a name that ties a series of related messages together\.
+ `message`: The message\. Remember that the wording is subject to change, so you should not automate against it\.

## Log levels and verbosities for encoder logs<a name="log-levels"></a>

To use this table, find a level in the first column then read across to identify the message severities that will appear in the logs with this logging level\.


| Level | Debug messages | Info messages | Warning messages | Critical messages | Fatal messages | 
| --- | --- | --- | --- | --- | --- | 
| DEBUG | Yes | Yes | Yes | Yes | Yes | 
| INFO |  | Yes | Yes | Yes | Yes | 
| WARNING |  |  | Yes | Yes | Yes | 
| ERROR |  |  |  | Yes | Yes | 

## Managing log storage<a name="manage-log-storage"></a>

When you delete a channel, the associated logs remain in CloudWatch Logs\. You will continue to be charged for their storage until you delete them\. To delete logs, change the log data retention\. All the data that is older than the retention setting that you specify will be deleted\. For more information, see [Amazon CloudWatch Logs User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/Working-with-log-groups-and-streams.html)\. The **Log group **for the logs is **ElementalMediaLive**\. 