# Modifying Actions in the Schedule \(Console\)<a name="schedule-modify"></a>

You can't modify an action in the schedule, even if it hasn't been received by the channel\. However, you can sometimes achieve a modify effect using a create action, a delete action, or both\.

## Modifying Actions Not Yet Started<a name="modify-action-not-started"></a>

You can't modify an action in the schedule, even if it hasn't been received by the channel\. 

To change an action that hasn't yet started, delete the action and create it again\. See the following sections for important tips on deleting and recreating\.

## Modifying an Input Switch Action<a name="schedule-modify-ips"></a>

You can't modify input switches in the schedule\. But you can achieve the same result by deleting the action and creating it again\. 

Keep in mind that you can't delete or create an action that has a start time less than 15 seconds in the future\. Give yourself enough time to delete and recreate the action before these deadlines\.

## Modifying an Input Switch Action in a Follow Chain<a name="schedule-modify-ips-follow"></a>

When you delete an action in a *follow chain* \(in order to delete and recreate it\), you must also delete and recreate the follow actions below this one\. You must do this because each action refers to the previous action\. If you delete the previous action, the next action becomes an orphan\. Orphans aren't permitted\. 

**Example 1: Modify an Action**  
For example, assume this is the follow chain:

```
Input A              Fixed    File
           Input B   Follow   File
           Input C   Follow   File
           Input D   Follow   File or Live
Input E              Fixed    File or Live
```

To delete and modify input A, you must also delete inputs B, C, and D\. You must delete input B to prevent it becoming an orphan\. The same rule applies until the next fixed input \(input E\), which isn't chained to another input\. Therefore, you aren't required to delete input E\.

When you delete input A using the console, a prompt appears to notify you that the follow actions below this action \(up to Input E, which is the next fixed input switch\) will also be deleted\. You can cancel or continue\. You must then recreate inputs A to D\. Recreate them in order going down the chain: input A, input B, input C, input D\.

**Example 2: Delete an Action**  
This example shows how to delete input B: 

```
Input A              Fixed    File
           Input B   Follow   File
           Input C   Follow   File
           Input D   Follow   File or Live
Input E              Fixed    File or Live
```

When you delete input B using the console, a prompt appears to notify you that the follow actions below this action \(up to Input E, which is the next fixed input switch\) will also be deleted\. You can cancel or continue\. You must then recreate inputs C and D\. Recreate them in order going down the chain: input C, input D\. Remember to set up input C to follow input A instead of input B\. 

## Inserting an Input Switch Action into a Chain<a name="schedule-insert-follow"></a>

To insert an action in a *follow chain* \(between two existing follow switch actions\), you must delete and recreate the follow actions below the insertion\. You do that to prevent two actions from following one previous action\. Branching is not allowed in the chain\. 

For example, suppose that you want to insert input X between input B and input C\. Input C already refers to input B\. You also want input X to refer to input B, but that is not allowed\. Therefore, you must delete input C and the inputs that follow\. You then recreate the chain in the following order: input X \(refers to input B\), input C \(refers to input X\), input D \(refers to input C\)\.

## Modifying an Image Overlay That Is in Progress<a name="schedule-modify-image-overlay"></a>

You can't directly modify an image overlay that is running in the channel\. But you can achieve the same result by creating a new action with the same layer specified\. You can do the following:
+ Shorten or extend the duration of an image overlay\.
+ Change one or more attributes\.
+ Specify an attribute that isn't currently specified in an image overlay\. For example, you might want to specify a fadeout where there is no fadeout in the current overlay\. 
+ Create a new action \(with a new action name\) that inserts an image overlay 15 seconds in the future\. Make sure to specify the following:
  + The same layer as the image that you want to modify\.
  + A duration that is appropriate \(the image doesn't inherit the duration of the current image\)\. 
  + All the attributes that you want\. 

  The new action replaces the current action because you specified the same layer\. 

## Modifying a SCTE\-35 Message That Is in Progress<a name="schedule-modify-scte35"></a>

You can't modify a SCTE\-35 message that is active in the channel\. Specifically, you can't shorten the duration of a splice\_insert\. But you can achieve the same result by creating a return\-to\-network action\. 