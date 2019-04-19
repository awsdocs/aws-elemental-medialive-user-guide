# Triggers for Blackout<a name="triggers-for-blackout"></a>

The blackout feature is triggered only by time\_signal messages of segmentation type **Other**\. It is not triggered by splice\_insert messages of any segmentation type, and is not triggered by time\_signal messages of any type except **Other**\. 

SCTE\-35 messages of type ID "splice insert" and messages of type ID "time signal" can both include "Other" time\_signal messages\. Therefore, when enabling blackout, the [ad avail mode](getting-ready-set-the-ad-avail-mode.md) is not relevant\. Blackout works the same with either mode\.

The segmentation ID triggers blackout based on “events,” as shown in the following table\.


| SCTE\-35 Segmentation Type | Blacked out | 
| --- | --- | 
| Chapter Start | Start blacking out | 
| Chapter End | End blacking out | 
| Network Start | End blacking out | 
| Network End | Start blacking out | 
| Program Start | Start blacking out | 
| Program End | End blacking out | 
| Unscheduled Event Start | Start blacking out | 
| Unscheduled Event End | End blacking out | 

For example, if the blackout feature is enabled, then blanking always occurs when a Program Start message is encountered and always ends when a Program End message is encountered\.

Note that the triggers for blackout on a Network event are different from the other events:
+ With Network, blanking starts when the Network *End* instruction is encountered\.
+ With other events, blanking starts when the "Event *Start*" instruction is encountered\.

**End Event Trigger Hierarchy**  
Events have the following "strength hierarchy\."


| SCTE\-35 Segmentation Type | Strength | 
| --- | --- | 
| Network | 1 \(Strongest\) | 
| Unscheduled Event | 2 | 
| Program | 3 | 
| Chapter | 4 \(Weakest\) | 

A blackout can be ended only by an event of equal or greater strength than the event that started it\.

For example, if the blackout is started by a Program Start, it can be ended by a Network Start, an Unscheduled Event End or a Program End\. It cannot be ended by a Chapter End\. MediaLive ignores the “end blackout” instruction implied by the Chapter End\.