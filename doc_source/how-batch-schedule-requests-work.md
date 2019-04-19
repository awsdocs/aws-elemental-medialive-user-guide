# How a Batch Request Works<a name="how-batch-schedule-requests-work"></a>

The intention of batching is to pass or fail all the actions together\. Therefore, AWS Elemental MediaLive validates batch actions together\. MediaLive performs the following validation:
+ It ensures that each action that is created or deleted has a UTC start time that is at least 15 seconds in the future\. 
+ If an action refers to an existing action in the schedule, it ensures that the reference to the existing action is correct\. For example, a follow input switch includes a reference to the action that it follows\. That action must exist\.

If the validation fails for any one action, it fails for all the actions in the batch\.

If you don't want the actions to pass or fail together, don't submit a batch\. Instead, create each action in its own batch update schedule command\.

If the validation succeeds, MediaLive processes all the delete requests before the create requests, regardless of the start times of the actions\.

**Example 1**  
An important use of batching is to execute several actions that must pass or fail together\. For example, suppose that you want to remove the corporate logo and immediately insert a splice\_insert \(in order to go to an ad avail\)\. To do that, you must create an action to remove the logo and another action to insert the splice\_insert\. However, you don't want MediaLive to insert the remove action if the splice\_insert action fails, or vice versa\. It's better if both actions fail because that allows you to fix the badly formed action, and then submit both actions again\.

You therefore submit the two actions together, in one batch update schedule command\. 

**Example 2**  
Another important use of batching is to fix an error in an action in the schedule\. For example, you might want to fix an image overlay that hasn't started yet and that was created with the wrong start time\. To do that, you submit one batch update schedule command with JSON that contains the following:
+ A payload to remove the original action to activate the image overlay\. This action has the incorrect start time\.
+ A payload to add a new action to activate the same image overlay\. This action has the correct start time\.