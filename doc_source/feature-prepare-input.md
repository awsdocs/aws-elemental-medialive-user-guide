# Preparing inputs in AWS Elemental MediaLive<a name="feature-prepare-input"></a>

You can prepare an input that is associated with an immediate input switch in order to reduce the delay that occurs when MediaLive performs the switch\. 

If you prepare an input, there is much less delay when MediaLive performs an immediate input switch\. This is because MediaLive has already probed the input and started to decode\. If you don't prepare the input, there is a delay between the moment that the MediaLive schedule receives the action and the moment that the switch occurs\.

We recommend that you prepare an input in this situation
+ You plan to switch to an input with an immediate start type\.
+ You don't know when the switch will need to occur, but you do know that you might have only a few seconds advance notice\.

You prepare an input by adding an *input prepare* action to the [channel schedule](working-with-schedule.md)\. Typically, the input switch that the input prepare applies to is an immediate input switch\. The input prepare itself can be set up to start at a fixed time, to start immediately, or to start following a specified input switch\. 

MediaLive adds the action to the schedule\. At the action start time, MediaLive starts to prepare the input\. 

Note that there is no advantage to preparing an input if you will switch to it as a fixed input switch or a follow input switch\. In this case, MediaLive automatically prepares the input ahead of time\.

**Terminology**  
In this section, we use the following terms:
+ *Prepare action *– The input prepare action in the schedule\.
+ *Associated switch action* – The input switch action that the input prepare action is associated with\. The prepare action prepares input A\. The associated switch action switches to input A\.
+ *Fixed prepare* – An input prepare action that is set up to start at a fixed time\. 
+ *Immediate prepare* – An input prepare action that is set up to start immediately\.
+ *Follow prepare, follow\-start prepare, follow\-end prepare* – An input prepare action that is set up to follow an input switch\. The follow prepare can follow the start or the end of the referenced switch\.
+ *Reference switch action* – The input switch action that is being used as the trigger for a follow input prepare\. So a follow input prepare follows the reference input switch action\.

**Note**  
This content in this section assumes that you are familiar with input switching, as described in [Input switching in AWS Elemental MediaLive](scheduled-input-switching.md)\. 

**Topics**
+ [Rules and limits for input prepare](input-prep-rules.md)
+ [Setting up input prepare actions in the schedule](prepare-input-procedure.md)
+ [How input prepare actions behave at runtime](input-prep-runtime.md)
+ [Modifying input prepare actions](input-prep-modify.md)
+ [Deleting and stopping input prepare actions](input-prep-delete.md)