# Handling the transition when the next input is follow<a name="transition-follow-success"></a>

When planning the schedule, you should ensure that a switch from one input to a "follow input" can succeed\.

A follow input \(input B\) won't succeed if the current input \(input A\) is set up to loop\. When AWS Elemental MediaLive reaches the file end, it starts to ingest again from the beginning of the file\. 

The **Source end behavior** field in each input attachment controls looping\. \(This field appears in the **Input attachments** page, in the **General input settings** section of the channel\.\) 
+ Always set the **Source end behavior** for input A to **CONTINUE**\. When input A finishes, the channel immediately switches to input B\.

When you create the channel, it is important to set the **Source end behavior** to **CONTINUE** in every input attachment where the next planned input in the schedule will be a follow input\. If you don't set up the input with **CONTINUE**, you won't be able to set up the schedule with the next input as a follow input\. You will have to cancel the schedule action, modify the input attachment, and try the schedule action again\.