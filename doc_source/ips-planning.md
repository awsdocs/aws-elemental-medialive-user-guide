# Planning the Schedule of Input Switches<a name="ips-planning"></a>

This section provides some guidelines for successfully setting up input switches in the channel\.

## Planning the Names<a name="ips-planning-names"></a>

When you set up MediaLive for a channel with multiple inputs, you create inputs, you associate the inputs with a channel by setting them up as input attachments, and in the schedule you create actions that reference the input attachments\.

In effect, the same video asset is referenced three times:
+ As an input
+ As an input attachment in a channel
+ As an action of type input switch in a schedule

Each of these representations has a name that you assign\. The default \(recommended\) input attachment name on the console is equal to the input name\. 

Given both of these points, you might want to consider using the same name for all these representations\. You might also want to establish a naming convention\. For example, for the naming convention you could include the type \(VOD or live\) plus a description, such as **vod\_ward\_cars\_ad** and **live\_studio\_feed**\.

You would then use the same name for all three representations\. For example, use **vod\_ward\_cars\_ad** as the name for the input, for the input attachment, and for the schedule action\.

## Handling the Transition When the Next Input is Fixed<a name="ips-transition-gap"></a>

When planning the schedule, you should ensure that there is no gap when switching from a file input \(input A\) to an input that starts at a fixed time \(input B\)\. Input B can be a file or a live input\. If the current input ends before the switch start time, there is potential for a gap\. 

The **Source end behavior** field in each input attachment controls the gap\. \(This field appears in the **Input attachments** page, in the **General input settings** section\.\) There are two options to ensure a smooth transition in this situation:
+ If you set the **Source end behavior** field for input A to **LOOP**, then when input A finishes, MediaLive goes back and ingests it again until the start time of input B occurs\. 
+ If you set the **Source end behavior** field for input A to **CONTINUE**, then input A is ingested only once; when the input finishes, the channel follows the behavior specified in the **Input Loss Behavior** set of fields \(although without the "repeat frames" logic\)\. When the start time of input B occurs, the input loss behavior ends and the channel switches to input B\.

  \(To display this field, in **General input settings** for **Global configuration**, for **Input loss behavior**, choose **Input loss behavior**\. More fields appear\.\)

## Handling the Transition When the Next Input is Follow<a name="transition-follow-success"></a>

When planning the schedule, you should ensure that a switch from one input to a "follow input" can succeed\.

A follow input \(input B\) won't succeed if the current input \(input A\) is set up to loop\. When MediaLive reaches the file end, it starts to ingest again from the beginning of the file\. 

The **Source end behavior** field in each input attachment controls looping \(This field appears in the **Input attachments** page, in the **General input settings** section\.\) 
+ Always set the **Source end behavior** for input A to **CONTINUE**\. When input A finishes, the channel immediately switches to input B\.

When you create the channel, it is important to set the **Source end behavior** to **CONTINUE** in every input attachment where the next planned input in the schedule will be a follow input\. If you don't set up the input with **CONTINUE**, you won't be able to set up the schedule with the next input as a follow input\. You will have to cancel the schedule action, modify the input attachment, and try the schedule action again\.