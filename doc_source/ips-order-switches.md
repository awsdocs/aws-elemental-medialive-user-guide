# Plan the order of input switches<a name="ips-order-switches"></a>

We recommend that you plan the order of the input switches before you create the actions in the schedule using the console or the CLI\.

**To plan the order of input switches**

1. In the first position, put the input attachment that you want MediaLive to ingest first\. Make a note that this input will be an immediate switch in the schedule\.

1. Make a list of switches and the input attachment to use for each switch\. Decide on the start type for each switch—fixed, immediate, or follow\. For more information, see [Fixed, immediate, and follow switches](ips-switch-types.md) and [Rules and limits for input switches](ips-limits.md)\. 

   You should be able to organize the fixed and follow input switches into an ordered list\. You might not be able to include the immediate switches in the ordered list because you don't know their start times\. See the [example](ips-step-plan-switches.md#ips-ordered-list-examples) after this procedure\.

   Note the following about switching to an input:
   + You can switch to an input attachment as many times as you want\.
   + When you switch to a dynamic input, you must provide the URL that applies for that usage of the dynamic input\. In the list that you make, specify the URL for each usage\.

1. Read the information later in this section about handling the transition between switches\. For each input attachment in your list, make a note of how to handle the transition\.

**About Models for the Schedule**  
There are two models for setting up input switches in the schedule:
+ In the recommended model, you use only the schedule to control the ingest of all inputs\. With this model, the order of the input attachments in the channel isn't relevant\. You set up the schedule so that the first input switch is an immediate switch to the input that you want to ingest first\. As soon as the channel starts and before the channel starts to ingest, the channel performs that immediate switch\.

  The steps earlier in this section show how to design the schedule for this model\.
+ In the other model, the first input attachment is the first input that MediaLive ingests\. You set up the schedule to perform its input switch only after that first ingest\. 

  We don't recommend this model because you must look at the order of input attachments and at the schedule\. With the first model, you monitor the order of ingest from one place—the schedule\.