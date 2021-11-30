# Working with the AWS Elemental MediaLive schedule<a name="working-with-schedule"></a>

In AWS Elemental MediaLive, you can manipulate the processing of a channel while it is running\. You perform this manipulation by adding actions to the schedule that is associated with the channel\. The schedule holds each action until the start time for the action, at which point MediaLive passes the action to the channel, and the channel performs the action\.

**Topics**
+ [Types of actions in the schedule](x-actions-in-schedule.md)
+ [Types of timing for actions](sched-timing-types.md)
+ [How schedule actions work](sched-how-actions-work.md)
+ [Working with the schedule \(console\)](schedule-using-console.md)
+ [Working with the schedule \(AWS CLI\)](schedule-using-cli.md)