# Restarting a Channel<a name="ips-restart-channel-multi-inputs"></a>

If you restart a channel that has multiple inputs set up for scheduled input switching, MediaLive looks at the schedule to determine which input should currently be running\. MediaLive then behaves as follows:
+ If that input is a live input, then MediaLive starts ingesting that input at the current frame\.
+ If that input is a file input set to start at a fixed time, then MediaLive starts ingesting that input at the start of the file\. It does not adjust for the difference between the scheduled time and the current time\. For example, assume that it is now 13:10:00 UTC\. The schedule specifies to switch to input X at 13:00:00\. MediaLive starts ingesting the file from the start, not from 10 minutes into the file\.
+ If the current input is ambiguous because there is a chain of "follow" inputs, then MediaLive ignores the "follow" inputs\. It finds the most recent "fixed" input that is in the past, relative to the UTC time at which you restart the channel\. It starts ingesting the input at the start of the file\.

  For example, assume the schedule looks like this:
  + Live input X with fixed start time of 11:00
  + File input A with fixed start time of 11:06
  + File input B with follow start time
  + File input C with follow start time
  + Live input D with fixed start time of 12:15

  Scenario 1: Assume the channel stopped at 11:04, when input X was active\. You restart the channel at 12:09\. The most recent "fixed" input switch relative to the current time is at 11:06\. It is a switch to file input A\. MediaLive goes to input A and starts ingesting that input from the beginning\. 

  Scenario 2: Assume the channel stopped at 11:04, when input X was active\. You restart the channel at 12:16\. The most recent "fixed" input switch relative to the current time is at 12:15\. It is a switch to live input D\. MediaLive goes to input D and starts ingesting\. 

  Scenario 3: Assume the channel stopped at 11:08, when input A was active\. You restart the channel at 12:14\. The most recent "fixed" input switch relative to the current time is at 11:06\. It is a switch to file input A\. MediaLive goes back to input A and starts ingesting\. It will ingest files A to C until 12:15, when it will switch to the live input\. It will ingest at least part of file A\. It might ingest files B and C\. But at 12:15 it will definitely switch to input D\.