# How schedule actions work<a name="sched-how-actions-work"></a>

This section describes how MediaLive handles each combination of [action type](x-actions-in-schedule.md) and [start type](sched-timing-types.md)\. 

## How input switch actions work<a name="x-actions-in-schedule-ips"></a>

You can set up an action to switch the input that the running channel is ingesting\. The channel stops ingesting the current input and starts ingesting the specified input\. 

The input must already be attached to the channel\. 

Before you add input switching actions to the schedule, read [Input switching in AWS Elemental MediaLive](scheduled-input-switching.md)\.

**Input switch with fixed start**  
When you create the action, you include a start time\. The start time for the action must be at least 15 seconds in the future but not more than 14 days in the future\. After that cutoff, MediaLive rejects the request to create the action\. 

After you have created the action, the action sits in the schedule\. Approximately 15 seconds before the start time, the schedule passes the action to the channel\. The channel sets up so that the input switches at the specified time\.

**Input switch with immediate start**  
When you create the action, you set the start type to *immediate*\. 

For an input switch in a standard channel \(a channel with two pipelines\), MediaLive internally sets the start time to 10 seconds in the future\. This delay ensures that the switch occurs at exactly the same time for the two pipelines\.

The schedule immediately passes the action to the channel\. The channel immediately starts to switch the input \(for a single\-pipeline channel\), or sets up to switch at the specified time \(for a standard channel\)\.

**Input switch with follow start**  
When you create the action, you specify the input switch action that you want this action to follow\. That *reference action* must be an input switch\. 

The input for the reference action must have a source end behavior of *Continue*\. To find the **Source end behavior** field, go to the **Create channel** page, find the input in the **Input attachment** list, and then find **General input settings**\. 

After you create the action, the action waits in the schedule\. Just before the reference action is due to finish, the schedule passes the action to the channel so that the channel can switch to the new input as soon as the current input has finished\.

## How input prepare actions work<a name="x-actions-in-schedule-prep"></a>

You can set up an action to prepare an input that is associated with an immediate input switch, in order to reduce the delay that occurs when MediaLive performs the switch\.

The input must already be attached to the channel\. However, there is no requirement for the input switch for this input to already exist in the schedule\. For example, input X must be *attached *to the channel\. You can create action A to prepare input X and later on you can create action B to switch to input X\. Or you can create action B and then create action A\.

Before you add input prepare actions to the schedule, read [Preparing inputs in AWS Elemental MediaLive](feature-prepare-input.md)\.

**Input prepare with fixed start**  
When you create the action, include a start time\. The start time for the action must be at least 15 seconds before the start time of the associated input switch, but not more than 14 days in the future\. After that cutoff, MediaLive rejects the request to create the action\. 

After you have created the action, the action sits in the schedule\. Approximately 15 seconds before the start time of the prepare action, the schedule passes the action to the channel\. The channel starts preparing the input\.

**Input prepare with immediate start**  
When you create the action, you set the start type to *immediate*\. 

The schedule immediately passes the action to the channel\. The channel immediately starts the prepare\.

**Input prepare with follow start**  
When you create the action, you specify the input switch action that you want this action to follow\. That *reference action* must be an input switch\.

The input for the reference action must have a source end behavior of *Continue*\. To find the **Source end behavior** field, go to the **Create channel** page, find the input in the **Input attachment** list, and then find **General input settings**\. 

After you create the action, the action waits in the schedule\. Just before the reference action is due to finish, the schedule passes the action to the channel\. As soon as the current input has finished, the channel switches to the new input\.

## How image overlay actions work<a name="x-actions-in-schedule-image-overlay"></a>

You can set up an action to insert and remove an image overlay on the video:
+ The activate image overlay action inserts an image overlay and activates it so that it is superimposed on the underlaying video\. If the image overlay information includes a duration, then at the appropriate time the image overlay is removed\.
+ The deactivate image overlay action removes an image overlay\. You therefore use this action to remove a currently running image overlay before the specified duration, or remove it when no duration is specified\.

For information about preparing the image overlay file that the action inserts, see [Working with image overlays](working-with-image-overlay.md)\.

**Activate or deactivate with fixed start**  
When you create the action, you include a start time\. The start time for the action must be at least 15 seconds in the future but not more than 14 days in the future\. After that cutoff, MediaLive rejects the request to create the action\. 

After you have created the action, the action sits in the schedule\. Approximately 15 seconds before the start time, the schedule passes the action to the channel\. At the start time, the channel inserts the image overlay or removes the image overlay from the video\.

**Activate or deactivate with immediate start**  
When you create the action, you set the start type to *immediate*\. 

The schedule immediately passes the action to the channel\. The channel immediately inserts the image overlay or removes the image overlay\.

## How motion graphics overlay works<a name="x-actions-in-schedule-mg"></a>

You can set up an action to insert and remove a motion graphics overlay on the video:
+ The activate motion graphics action inserts a motion graphic and activates it so that it is superimposed on the underlaying video\. If the image overlay information includes a duration, then at the appropriate time the motion graphic is removed\.
+ The deactivate motion graphics action removes an image overlay\. You therefore use this action to remove a currently running motion graphics before the specified duration, or remove it when no duration is specified\.

For information about preparing the motion graphics asset that the action inserts, see [Working with motion graphics overlays](feature-mgi.md)\.

**Activate or deactivate with fixed start**  
When you create the action, you include a start time\. The start time for the action must be at least 15 seconds in the future but not more than 14 days in the future\. After that cutoff, MediaLive rejects the request to create the action\. 

After you have created the action, the action sits in the schedule\. Approximately 15 seconds before the start time, the schedule passes the action to the channel\. At the start time, the channel inserts the motion graphic or removes the motion graphic from the video\.

**Activate or deactivate with immediate start**  
When you create the action, you set the start type to *immediate*\. 

The schedule immediately passes the action to the channel\. The channel immediately inserts the motion graphic or removes the motion graphic\.

## How SCTE\-35 actions work<a name="x-actions-in-schedule-SCTE35"></a>

You can set up an action to insert a SCTE\-35 message in the channel\. There are three types of actions:
+ Action to insert a splice\_insert into the channel: a SCTE\-35 message with splice\_command\_type set to splice\_insert\.
+ Action to insert a time\_signal into the channel: a SCTE\-35 message with splice\_command\_type set to time\_signal\.
+ Action to insert a SCTE\-35 return\-to\-network message into the schedule in order to end a splice\_insert that either has a duration or has no duration\.

Before you add SCTE\-35 actions to the schedule, read [SCTE\-35 message processing](scte-35-message-processing.md)\.

**Insert SCTE\-35 message with fixed start**  
When you create the action, you include a start time\. The start time for the action must be at least 15 seconds in the future but not more than 14 days in the future\. After that cutoff, MediaLive rejects the request to create the action\. 

After you have created the action, the action sits in the schedule\. Approximately 15 seconds before the start time, the schedule passes the action to the channel\. At the start time, the channel inserts the SCTE\-35 message into the stream\.

After the channel inserts the message, MediaLive processes the inserted message in the same way as it processes messages that were already in the source content\. 

**Insert SCTE\-35 message with immediate start**  
When you create the action, you set the start type to *immediate*\. 

The schedule immediately passes the action to the channel\. The channel immediately inserts the SCTE\-35 message into the stream\.

After the channel inserts the message, MediaLive processes the inserted message in the same way as it processes messages that were already in the source content\. 

**Insert SCTE\-35 message with follow start**  
When you create the action, you specify the input switch action that you want this action to follow\. That *reference action* must be an input switch\.

The input for the reference action must have a source end behavior of *Continue*\. To find the **Source end behavior** field, go to the **Create channel** page, find the input in the **Input attachment** list, and then find **General input settings**\. 

After you create the action, the action waits in the schedule\. Just before the reference action is due to finish, the schedule passes the action to the channel\. As soon as the current input has finished, the channel inserts the SCTE\-35 message into the stream\.

After the channel inserts the message, MediaLive processes the inserted message in the same way as it processes messages that were already in the source content\. 

## How ID3 metadata and tags actions work<a name="x-actions-in-schedule-id3"></a>

You can set up an action to insert ID3 data in the channel\. There are two types of actions:
+ Action to insert ID3 metadata in outputs where ID3 [passthrough is enabled](enable-passthrough-id3.md)\. 

  You must specify a fully formed ID3 metadata item \(including both a header and a frame, as per the ID3 specification\) and encode it as base64\. MediaLive inserts the metadata once, at the time that you specify\.
+ Action to insert an ID3 tag in each segment in HLS and MediaPackage output packages where ID3 [passthrough is enabled](enable-passthrough-id3.md)\. 

  You specify the ID3 tag as plaintext\. MediaLive inserts the tag in every segment\.

Before you add ID3 metadata actions to the schedule, read [Working with ID3 metadata](id3-metadata.md)\.

Before you add ID3 segment tag actions to the schedule, read [Working with ID3 segment tags](id3-segment-tag.md)\.

**Insert ID3 data with fixed start**  
When you create the action, you include a start time\. The start time for the action must be at least 15 seconds in the future but not more than 14 days in the future\. After that cutoff, MediaLive rejects the request to create the action\. 

After you have created the action, the action sits in the schedule\. Approximately 15 seconds before the start time, the schedule passes the action to the channel\. At the start time, the channel inserts the data into the channel\.

After the channel inserts the message, MediaLive processes the data in the same way as it processes ID3 data that was already in the source content\. 

**Insert ID3 data with immediate start**  
When you create the action, you set the start type to *immediate*\. 

The schedule immediately passes the action to the channel\. The channel immediately inserts the data into the channel\.

After the channel inserts the message, MediaLive processes the data in the same way as it processes ID3 data that was already in the source content\. 

## How pause and unpause actions work<a name="x-actions-in-schedule-pause"></a>

You can insert an action to pause and unpause one or both pipelines in the channel\. The action pauses the specified pipelines and unpauses any unspecified pipelines:
+ Action with *one* pipeline specified–The action pauses the specified pipeline and unpauses the other pipeline\.
+ Action with *both* pipelines specified–The action pauses both pipelines\.
+ Action with *no* pipelines specified–The action unpauses both pipelines\. 



**Note**  
The pipelines that you don't specify are not left in their current state\. They are always set to unpaused\.

**Pause or unpause with fixed start**  
When you create the action, you include a start time\. The start time for the action must be at least 15 seconds in the future but not more than 14 days in the future\. After that cutoff, MediaLive rejects the request to create the action\. 

After you have created the action, the action sits in the schedule\. Approximately 15 seconds before the start time, the schedule passes the action to the channel\. At the start time, the channel pauses or unpauses the pipelines in the channel\.

**Pause or unpause with immediate start**  
When you create the action, you set the start type to *immediate*\.

The schedule immediately passes the action to the channel\. The channel immediately pauses or unpauses the pipelines in the channel\.