# Recommended Procedure<a name="ips-recommended-procedure"></a>

Every channel has a schedule\. In a channel that has multiple inputs, the schedule controls the order and timing of switches from one input to another\. There is nothing in the channel that implies an order, other than that the first input listed is ingested first if the schedule does not override it with an input switch\.

Therefore, when your channel includes input switching, you must add switch actions to the schedule\. It is a good idea to plan the schedule before you create the channel, and to add actions to the schedule before you start the channel\. 

This is the recommended order of work for setting up for input switching in a channel\. This order of work assumes that either you are already familiar with working with channels and inputs, or that you will read the chapters referred to in the following list, in order to understand how they work:

1. Plan the channel in the usual way, with these additions:
   + Assessing the upstream system: Make sure that you read the information for making sure the inputs are ready to be switched to\. See [Setting Up the Upstream System](setting-up-upstream.md)\.
   + Planning the input: Make sure that you read the information about assessing [video and audio](planning-the-input.md) for multiple inputs\.

1. Plan the schedule of input switches\. See [ Planning the Schedule of Input Switches ](ips-planning.md)\.

1. Create the inputs\. See [Creating Inputs for Input Switching](ips-creating-inputs.md)\.

1. Create the channel and attach the inputs\. See [Creating a Channel with Multiple Inputs](ips-create-channel-multi-inputs.md)\.

1. Add switch actions to the schedule\. See [Setting Up the Schedule with Input Switches](ips-set-up-schedule.md)\.

1. Start the channel\. See [ Starting a Channel That Has Multiple Inputs ](ips-start-channel-multi-inputs.md)\.