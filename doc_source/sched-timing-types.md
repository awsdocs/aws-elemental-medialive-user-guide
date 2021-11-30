# Types of timing for actions<a name="sched-timing-types"></a>

There are several ways to specify the timing for an action:
+ Fixed – Perform the action at a specific time that you specify\.

  For most actions, the specified time must be at least 15 seconds in the future\. For input prepare actions, the specified time must be at least 15 seconds before the start of the associated input switch\. 
+ Immediate – Perform the action as soon as possible\. 

  You don't specify a time\.
+ Follow – Perform the action just before the specified input switch starts, or just after the currently running input has finished\. 

The following table shows the types of timing that apply to each type of action\. To read this table, find an action in the first column, then read across the row for the applicable types of timing\.


| Type of action | Supported types of timing |  | Fixed | Follow \(Note A\) | Immediate | 
| --- | --- | --- | --- | --- | --- | 
| Switch the input \(perform an input switch\) | Yes | Yes | Yes | 
| Prepare the input \(perform an input prepare\) | Yes | Yes | Yes | 
| Activate a static image overlay | Yes |  | Yes | 
| Activate a motion graphics overlay | Yes |  | Yes | 
| Deactivate a static image overlay | Yes |  | Yes | 
| Deactivate a motion graphics overlay | Yes |  | Yes | 
| Insert a SCTE\-35 message | Yes | Yes | Yes | 
| Insert ID3 metadata | Yes |  | Yes | 
| Insert an ID3 segment tag | Yes |  | Yes | 
| Pause or unpause one or both pipelines | Yes |  | Yes | 

**Note A**  
With a follow, the applicable action can follow an input switch\. It can't follow other types of actions\. Therefore, the action that is *being followed *is always an input switch\. The action that does the follow is an input switch, an input prepare, or a SCTE\-35 message\. 