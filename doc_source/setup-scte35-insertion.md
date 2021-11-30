# Inserting SCTE\-35 messages using the schedule<a name="setup-scte35-insertion"></a>

Use the [channel schedule](sched-how-actions-work.md#x-actions-in-schedule-SCTE35) to insert SCTE\-35 messages in the content\. For example, you can add an action in the channel schedule to insert a splice insert in the running channel at a specific time\. 

The main use case for this feature is to add SCTE\-35 messages, when the source content doesn't already include SCTE\-35 messages\. 

To insert SCTE\-35 messages in the content, create actions in the schedule\. For detailed information, see [Working with the AWS Elemental MediaLive schedule](working-with-schedule.md)\.

After MediaLive inserts the SCTE\-35 message in the channel, MediaLive processes the message in the same way as it would process SCTE\-35 messages that were in the input\. You define this processing when you create the channel and configure these options:
+ Blanking
+ Blackout
+ Manifest decoration
+ Passthrough

For a summary of these options, see [Scope of processing by feature](scope-by-feature.md) and [Supported features by output type](processing-applicability-by-output-type.md)\. 