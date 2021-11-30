# Starting and restarting a channel that has multiple inputs<a name="ips-start-channel-multi-inputs"></a>

After you create the channel and add actions to its schedule, you can start the channel\.

Before you start the channel, make sure that the inputs attached to the channel are ready:
+ Push inputs must be already pushing before you start the channel\. A push input must be already pushing even if it isn't the first input in the channel\.
+ If the first input in the channel is a file input, it must be ready to be pulled\. 
+ A file input that isn't the first input doesn't have to be ready to be pulled until approximately 30 seconds before the switch to the input occurs\. 

**Topics**
+ [What happens at runtime](#ips-runtime-behavior)
+ [Restarting a channel](#ips-restart-channel-multi-inputs)
+ [What happens with an empty schedule](#ips-empty-channel-charges)

## What happens at runtime<a name="ips-runtime-behavior"></a>

When you start the channel, AWS Elemental MediaLive takes a short time to get the channel ready to run\. 

As soon as the channel is ready, MediaLive looks at the schedule to determine if there is an input switch with an immediate switch, with a start time that is now or with a start time that is overdue: 
+ If it finds this action, it switches to that input and starts ingesting\. 
+ If it doesn't find this action, it starts ingesting the first input attachment listed in the channel\.

If you set up the channel and schedule as recommended, then as soon as the channel is ready, it finds an immediate switch to the first input that you want MediaLive to ingest\. 

## Restarting a channel<a name="ips-restart-channel-multi-inputs"></a>

If you restart a channel that has multiple inputs set up for scheduled input switching, AWS Elemental MediaLive looks at the schedule to determine which input should currently be running\. MediaLive then behaves as follows:
+ If that input is a live input, then MediaLive starts ingesting that input at the current frame\.
+ If that input is a file input set to start at a fixed time or immediately, then MediaLive starts ingesting that input at the start of the file or of the file clip \(if you clipped the input\)\. It doesn't adjust for the difference between the scheduled time and the current time\. For example, assume that it is now 13:10:00 UTC\. The schedule specifies to switch to input X at 13:00:00\. MediaLive starts ingesting the file from the start, not from 10 minutes into the file\.
+ If the current input is ambiguous because there is a chain of follow inputs, then MediaLive ignores the follow inputs\. It finds the most recent fixed or immediate input that is in the past, relative to the UTC time at which you restart the channel\. It starts ingesting the input at the start of the file\.

  For example, assume the schedule looks like this:
  + Live input X with fixed start time of 11:00
  + File input A with fixed start time of 11:06
  + File input B with follow start time
  + File input C with follow start time
  + Live input D with fixed start time of 12:15

  Scenario 1: Assume the channel stopped at 11:04, when input X was active\. You restart the channel at 12:09\. The most recent fixed input switch relative to the current time is at 11:06\. It is a switch to file input A\. MediaLive goes to input A and starts ingesting that input from the beginning\. 

  Scenario 2: Assume the channel stopped at 11:04, when input X was active\. You restart the channel at 12:16\. The most recent fixed input switch relative to the current time is at 12:15\. It is a switch to live input D\. MediaLive goes to input D and starts ingesting\. 

  Scenario 3: Assume the channel stopped at 11:08, when input A was active\. You restart the channel at 12:14\. The most recent fixed input switch relative to the current time is at 11:06\. It is a switch to file input A\. MediaLive goes back to input A and starts ingesting\. It ingests files A to C until 12:15, when it switches to the live input\. It ingests at least part of file A\. It might ingest files B and C\. But at 12:15 it definitely switches to input D\.

## What happens with an empty schedule<a name="ips-empty-channel-charges"></a>

If the channel finishes the last input in the schedule \(so that the schedule is now empty\) and you have set up so that the input doesn't loop, then MediaLive stops ingesting, but the channel continues to run\. Charges for the channel continue to accrue\.