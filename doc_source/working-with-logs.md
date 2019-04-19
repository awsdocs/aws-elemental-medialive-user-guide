# Working with Logs<a name="working-with-logs"></a>

You view MediaLive logs on the CloudWatch Logs console, in the same way that you view logs for any service\. 

You don't have to set up the logs, logging groups, or log streams on the CloudWatch Logs console because MediaLive automatically sets them up for you\. 

The log group is always the following: **ElementalMediaLive**\.

The log stream is named after the ARN/pipeline\. For example, `arn_aws_medialive_us-west-2_111122223333_channel_5106412_0`, where `5106412` is the channel ID and `0` is the pipeline\.

## Content of EML Logs<a name="content-logs"></a>

The MediaLive logs are in JSON format:

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
+ `severity`: A letter\. The logging level \(which you set when you enable logging\) controls which severities could appear in logs\. For more information, see [Log Levels and Verbosities](#log-levels.title)\.
+ `timestamp`: The time in ISO 8601 format: yyyy \- mm \- dd T hh : mm : ss : decimal fraction of second\.
+ `channel_arn`: The ARN plus the channel ID\. In the preceding example, the channel has ID `5106412`\.
+ `logger_name`: This might be blank or might specify a name that ties a series of related messages together\.
+ `message`: The message\. Remember that the wording is subject to change, so you should not automate against it\.

## Log Levels and Verbosities<a name="log-levels"></a>

To use this table, find a level in the first column then read across to identify the message severities that will appear in the logs with this logging level\.


| Level | Debug Messages | Info Messages | Warning Messages | Critical Messages | Fatal Messages | 
| --- | --- | --- | --- | --- | --- | 
| DEBUG | Yes | Yes | Yes | Yes | Yes | 
| INFO |  | Yes | Yes | Yes | Yes | 
| WARNING |  |  | Yes | Yes | Yes | 
| ERROR |  |  |  | Yes | Yes | 

## Managing Log Storage<a name="manage-log-storage"></a>

When you delete a channel, the associated logs remain in CloudWatch Logs\. You will continue to be charged for their storage until you delete them\. To delete logs, change the log data retention\. All the data that is older than the retention setting that you specify will be deleted\. For more information, see [Amazon CloudWatch Logs User Guide](https://docs.aws.amazon.com//AmazonCloudWatch/latest/logs/Working-with-log-groups-and-streams.html)\. The **Log group **for the logs is **ElementalMediaLive**\. 