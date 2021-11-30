# Deleting actions from the schedule<a name="ips-manage-schedule"></a>

You can delete input switch actions from the schedule\. There are different rules for deleting actions depending on the current state of the channel\. The channel can be running, idle, or recovering\. The channel is idle if you manually stopped it\. The channel is recovering if it failed and MediaLive is automatically restarting it\.

**Deleting actions while the channel is running**  
When the channel is running, there are restrictions on the input switch actions that you can delete\. MediaLive must preserve information about the currently active input\. It must preserve that information so that if the channel fails, MediaLive can recover and start ingesting on the appropriate input\. Therefore, this rule applies:
+ You can't delete the most recent fixed or immediate input switch\. The term *most recent* means one of the following:
  + The input is the input currently being ingested\. So the most recent input and the active input are the same\.
  + The input is the fixed or immediate input switch that most recently ingested\. The active input might be a follow input\.
+ You can't delete any of the actions in a follow chain that follows this most recent fixed or immediate input switch\. For example, in the following diagram, assume that input A is the most recent fixed or immediate input switch\. You can't delete actions B, C, or D\. You can delete E, which is not part of the follow chain\.

  ```
     Input A    Fixed
       Input B  Follow
       Input C  Follow 
       Input D  Follow
     Input E    Immediate
  ```

**Deleting actions while the channel is idle**  
You can delete an input switch action when the channel is idle, so long as the action is still in the schedule\. 

To delete an action that is in a follow chain, you must delete the entire follow chain, then recreate the follow chain but omitting the unwanted action\. See [Deleting actions from the schedule \(console\)](schedule-using-console-delete.md)\.

**Deleting actions while the channel is recovering**  
You can delete input switch actions while the channel is recovering\.