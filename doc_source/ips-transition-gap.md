# Handling the transition when the next input is fixed or immediate<a name="ips-transition-gap"></a>

When planning the schedule, you should ensure that there is no gap when switching from a file input \(input A\) to an input \(input B\) that starts at a fixed time or that starts immediately\. Input B can be a file or a live input\. If the current input ends before the switch start time, there is potential for a gap\. 

The **Source end behavior** field in each input attachment controls the gap\. \(This field appears in the **Input attachments** page, in the **General input settings** section of the channel\.\) There are two options to ensure a smooth transition in this situation:
+ If you set the **Source end behavior** field for input A to **LOOP**, then when input A finishes, MediaLive goes back and ingests it again until the start time of input B occurs\. 
+ If you set the **Source end behavior** field for input A to **CONTINUE**, then input A is ingested only once; when the input finishes, the channel follows the behavior specified in the **Input Loss Behavior** set of fields \(although without the "repeat frames" logic\)\. When the start time of input B occurs, the input loss behavior ends and the channel switches to input B\.

  \(To display this field, in **General input settings** for **Global configuration**, for **Input loss behavior**, choose **Input loss behavior**\. More fields appear\.\)