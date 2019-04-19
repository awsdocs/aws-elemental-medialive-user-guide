# Typical Use Cases<a name="typical-use-cases"></a>

Scheduled input switching supports the following use cases\.

## Use Case 1: One Live Feed and One File Input Alternating<a name="ips-case-1"></a>

You have a channel to process a live \(streaming\) feed from a specific source, perhaps for a sports tournament\. Periodically \(perhaps between individual sports events\), the live feed should be replaced by file content \(perhaps a filler such as a video of ocean waves\)\. After a few minutes, the same live feed should be resumed\. 

You set up the channel with one live input and one file input\. The first input is the live input\. 

Before you start the channel, you create a schedule that consists of actions to switch to the live input at the top of each hour—at 10:00 AM, 11:00 AM, and so on\. 

You then start the channel\. As soon as each sports event has finished, you modify the schedule "on the spot" to switch to the video filler\. The live feed continues for a few moments \(perhaps showing the sports crowd or the players leaving the stadium\), and then the channel switches to the filler video\. At the top of each hour, the channel switches to the live feed\.

## Use Case 2: One Live Feed and File Inputs, and the Channel Starts with a File Input<a name="ips-case-2"></a>

You have the same requirements as for use case 1, except that you want to start the channel with a file clip, perhaps from the opening of the sports event\. At the top of the first hour, you want to show the video filler\. But at the top of the second and succeeding hours, you want to show highlights from earlier in the day\.

You set up the channel with one live event \(a live input\) and several file inputs: one for the opening, one for the video filler, and several for the highlights\. The first input is the file input for the opening event\. 

Before you start the channel, you create a schedule that contains one action to switch to the live input as soon as the file input has finished\. 

You then start the channel\. As time goes on, you modify the schedule to add more actions, as for use case 1, to switch back and forth between the live input and the file inputs\.

## Use Case 3: Two Live Feeds<a name="ips-case-3"></a>

You have a channel to process live feed from two different sources\. You want to insert ad content into the channel, as required\. You want to insert this ad content using MediaLive\. \(You do not want to insert SCTE\-35 messages that a downstream system will read in order to replace the avails with ad content\.\)

The live feeds might be the venue feed and the in\-studio feed for the same sports event\. You want to switch from one live feed to the other\. You want to time the switches "on the spot" instead of according to a strict clock schedule\. Occasionally, you want to switch from one live feed to an ad\. When the ad is finished, you might want to return to one of the live feeds\.

You set up the channel with two live inputs and several file inputs \(one file for each ad\)\. 

Before you start the channel, you create a schedule that contains the first action in the schedule\. That action is to switch to the first input, input A, that you want to the channel to ingest\. You set the start time for input A to a time that is at least one minute earlier than the time that you start the schedule\. You then start the channel\. MediaLive immediately reads the schedule and switches to the input that is supposed to be the current action, which is input A\. When appropriate, you modify the schedule on the spot to add actions to queue up one or more switches\.