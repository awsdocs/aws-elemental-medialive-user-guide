# Blackout Restriction Flags<a name="blackout-restriction-flags"></a>

**Restrictions in the Input**  
The segmentation descriptors in messages that are blackout triggers always include two types of flags\. These flags provide additional information as guidance for blackout in specific situations:
+ web\_delivery\_allowed\_flag
  + True means that there is no restriction on including the event’s content in a stream that is intended for web delivery\. There is no need to black out content in streams intended for web delivery\. 
  + False means that there is a restriction\. The content should be blacked out\. 
+ no\_regional\_blackout\_flag
  + True means that there is no restriction on including the event’s video in a stream intended for regional markets\. There is no need to black out content in streams intended for regional markets\. 
  + False means that there is a restriction\. The content should be blacked out\.

If both flags are present \(which is usually the case; it is unusual to have only one flag present\), then a “false” for one flag takes precedence over a “true” for the other flag\. Blackout should occur\.

Typically, in any message in the input only one of these flags is ever set to false, so only one restriction is ever in place\. There would typically never be both a regional delivery restriction and a web delivery restriction\. This is because if content is considered restricted for regional delivery, then it would not also be considered restricted for web delivery \(where the concept of a region makes no sense\)\.

To summarize, this is the blackout logic that applies to each event that is encountered\.


|  | Content of corresponding SCTE\-35 message: Web delivery allowed? | Content of corresponding SCTE\-35 message: Regional delivery allowed? | Result | Comment | 
| --- | --- | --- | --- | --- | 
| S1 | Flag is not present | Flag is not present | Blackout occurs | Never occurs in messages that are blackout triggers | 
| S2 | Flag is set to "true" | Flag is set to "true" | Blackout doesn't occur |  | 
| S3 | Flag is set to "true" | Flag is set to "false" | Blackout occurs |  | 
| S4 | Flag is set to "false" | Flag is set to "true" | Blackout occurs |  | 

**MediaLive Handling of Restrictions**  
You can modify this default blackout behavior by instructing MediaLive to ignore a restriction flag that is set to false, so that blackout will *not *occur for this event\. In other words, to use this logic, "Even if the message indicates to black out content because a regional blackout is in place, do not follow this instruction\. Ignore the fact that a regional blackout is in place and do not black out content"\.

You modify the behavior by setting fields in the channel\. 