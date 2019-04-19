# Actions in the Schedule<a name="x-actions-in-schedule"></a>

The schedule is a list of actions that a channel executes as it is running\. You create the actions in the schedule, and you set either a fixed or relative time that specifies when you want the channel to execute each action\.

MediaLive stores the actions in the schedule\. Shortly before its start time, each action is received by the channel\. At the action start time, the channel executes the action\.

You can delete an action from the schedule up to the moment that the channel receives it\.

## Types of Schedule Actions for Input Switching<a name="x-actions-in-schedule-input-switching"></a>
+ Action to switch the input that the running channel is ingesting\. The action specifies when to execute the switch, either at a specific \(*fixed*\) time, or to *follow* when the currently running input is finished\.

  When the channel executes this action, the channel stops ingesting the current input and starts ingesting the specified input\.

  With input switching, the channel must already be set up with all the inputs that you want to switch to\. You can't use a switch action to insert an input into the list of inputs in the channel\. You can use it only to switch among the inputs that are already in the list\.

  After you create an action, the action waits in the schedule\. The channel receives the action 15 seconds before the action's designated start time\. At the start time, the channel executes the action\. 

Before you add input switching actions to the schedule, read [Input Switching in AWS Elemental MediaLive](scheduled-input-switching.md)\.

## Types of Schedule Actions for Image Overlay<a name="x-actions-in-schedule-image-overlay"></a>
+ Action to activate a static image overlay\. An image overlay is an image that is layered over the underlying video\.

  When a channel executes this action, the image overlay is superimposed on the video\. If the image overlay information includes a duration, then at the appropriate time the image overlay is removed\.
+ Action to deactivate a static image overlay\.

  When the channel executes the deactivate action, the image overlay is removed\. You therefore use this action to remove a currently running image overlay before the specified duration, or remove it when no duration is specified\.

After you create an action, the action waits in the schedule\. The channel receives the action 15 seconds before the action's designated start time\. At the start time, the channel executes the action\. 

**Note**  
You remove the active image from the video by creating a deactivate action\. You don't deactivate the image by deleting the activate action from the schedule\. \(In fact, deleting the action has no effect because its start time has passed\.\)

Before you add image overlay actions to the schedule, read [Working with Image Overlays](working-with-image-overlay.md)\.

## Types of Schedule Actions for SCTE\-35<a name="x-actions-in-schedule-SCTE35"></a>
+ Action to insert a splice\_insert into the channel: a SCTE\-35 message with splice\_command\_type set to splice\_insert\.
+ Action to insert a time\_signal into the channel: a SCTE\-35 message with splice\_command\_type set to time\_signal\.
+ Action to insert a SCTE\-35 return\-to\-network message into the schedule in order to end a splice\_insert that either has a duration or has no duration\.

After you create an action, the action waits in the schedule\. The channel receives the action 15 seconds before the action's designated start time\. At the start time, the channel executes the action\. 

Before you add SCTE\-35 actions to the schedule, read [SCTE\-35 Message Processing](scte-35-message-processing.md)\.

## Types of Schedule Actions for ID3 Metadata<a name="x-actions-in-schedule-ID3"></a>
+ Action to insert ID3 metadata in outputs where ID3 [passthrough is enabled](enable-passthrough-id3.md)\. You must insert a fully formed ID3 metadata item \(including both a header and a frame, as per the ID3 specification\) and encode it as base64\. You specify a start time for inserting the metadata\. 

After you create an action, the action waits in the schedule\. The channel receives the action 15 seconds before the action's designated start time\. At the start time, the channel executes the action\. 

Before you add ID3 metadata actions to the schedule, read [Working with ID3 Metadata](id3-metadata.md)\.

## Types of Schedule Actions for Pause<a name="x-actions-in-schedule-pause"></a>
+ Action to pause the specified pipeline or pipelines in the channel\. By implication, any pipelines that you don't include in the action are automatically set to unpause\. You must specify a start time for the pause action\. 
+ Action to unpause a pipeline or pipelines that is currently paused\. You must specify a start time for the unpause action\.

After you create an action, the action waits in the schedule\. The channel receives the action 15 seconds before the action's designated start time\. At the start time, the channel executes the action\. 

**Note**  
You unpause \(stop the pause\) on the pipeline by creating an unpause action\. You don't stop the pause by deleting the pause action from the schedule\. \(In fact, deleting the action has no effect because its start time has passed\.\)