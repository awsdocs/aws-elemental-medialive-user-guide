# Setting up input prepare actions in the schedule<a name="prepare-input-procedure"></a>

Follow this procedure to add input prepare actions to the channel schedule, in order to prepare any input ahead of the switch action to that input\.

**To include input prepare actions in a channel schedule**

1. As a one\-time action, enable the input prepare feature in the channel\. You must enable the feature while the channel is idle\. See [Enabling and disabling the input prepare feature](input-prep-enable.md)\.

1. Plan the input switches and input prepares for the channel\. See [Planning the start type for an input prepare](input-prep-plan-start.md)\.

1. If the associated input switch includes input clipping, see [Input clipping](input-clipping.md)\.

   If the associated input switch is an input failover pair, see [Dynamic inputs](dynamic-inputs.md)\.

1. Create the actions in the schedule\. Typically, you create some prepare actions and switch actions before you start the channel for the first time\. Then you add more actions over time\. You add fixed switch actions, and follow switch actions\. You add prepare actions as soon as you know that you will have an immediate switch some time in the future\. Typically, you add all these actions while the channel is running, but you can also add them when the channel is idle\.

   For detailed information on adding an input prepare action to the schedule, see [Working with the AWS Elemental MediaLive schedule](working-with-schedule.md)\.

**Topics**
+ [Enabling and disabling the input prepare feature](input-prep-enable.md)
+ [Planning the start type for an input prepare](input-prep-plan-start.md)
+ [Input prepare and dynamic inputs](#input-prep-dynamic)
+ [Input prepare with clipping](input-prep-clip.md)
+ [Input prepare and automatic input failover](input-prep-aif.md)

## Input prepare and dynamic inputs<a name="input-prep-dynamic"></a>

You can prepare for an input switch when the associated input is a [dynamic input](dynamic-inputs.md)\. A dynamic input has a variable in its path\. Each time that you add the input to the schedule, you specify a *replacement string* to replace the variable with a file\.

When you set up the prepare input action, you must specify this replacement string\. The string must exactly match the replacement string in the switch action\. If the strings are not identical, MediaLive won't prepare the input in advance\.

You might use this dynamic input more than once in the channel, and the replacement string might be different in each instance\. Make sure that you change the string in each prepare action\.