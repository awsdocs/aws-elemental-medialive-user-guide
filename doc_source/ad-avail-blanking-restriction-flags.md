# Ad Avail Blanking Restriction Flags<a name="ad-avail-blanking-restriction-flags"></a>

**Restrictions in the Input**  
SCTE\-35 messages of type time\_signal always contain segmentation descriptors\. 

SCTE\-35 messages of type splice\_insert might or might not include segmentation descriptors\.

If the input has SCTE\-35 messages that do include segmentation descriptors, these segmentation descriptors always include two types of flags\. Each flag has a value of "true" or "false" and provides additional information as guidance for blanking in specific situations:
+ web\_delivery\_allowed\_flag 
  + True means that there is no restriction on including the ad avail event’s content in a stream that is intended for web delivery: there is no need to blank out content in streams intended for web delivery\. 
  + False means there is a restriction: the content should be blanked out\. 
+ no\_regional\_blackout\_flag

  \(The wording of this flag is confusing\. Think of it as the "regional\_delivery\_allowed\_flag"\.\)
  + True means that there is no restriction on including the ad avail event’s video in a stream that is intended for regional markets: there is no need to blank out content in streams intended for regional markets\. 
  + False means there is a restriction: the content should be blanked out\.

If neither flag is present \(usually the case with splice\_inserts\), then both are considered to be false\. Blanking should occur\.

If both flags are present \(which is usually the case; it is unusual to have only one flag present\), then a “false” for one flag takes precedence over a “true” for the other flag\. Blanking should occur\.

Typically, in any message in the input only one of these flags is ever set to false, so only one restriction is ever in place\. There would typically never be *both* a regional delivery restriction and a web delivery restriction\. This is because if content is considered restricted for regional delivery, then it would not also be considered restricted for web delivery \(where the concept of a region makes no sense\)\.

To summarize, this is the blanking logic that applies to each ad avail event that is encountered\.


**Blanking Logic for Ad Avail Events**  

|  | Content of corresponding SCTE\-35 message: Web delivery allowed? | Content of corresponding SCTE\-35 message: Regional delivery allowed? | Result | Comment | 
| --- | --- | --- | --- | --- | 
| S1 | Flag is not present | Flag is not present | Blanking occurs | This combination can only occur in a message type splice\_insert \(where the segmentation descriptor is optional\)\. | 
| S2 | Flag is set to "true" | Flag is set to "true" | Blanking doesn't occur |  | 
| S3 | Flag is set to "true" | Flag is set to "false" | Blanking occurs |  | 
| S4 | Flag is set to "false" | Flag is set to "true" | Blanking occurs |  | 

**MediaLive Handling of Restrictions**  
You can modify this default blanking behavior by instructing MediaLive to ignore a restriction flag that is set to false, so that blanking does *not * occur for this ad avail event\. In other words, use this logic: "Even if the message indicates to blank content because a regional blackout is in place, do not follow this instruction\. Ignore the fact that a regional blackout is in place and do not blank content"\.

You modify the behavior by setting fields in the channel\. See [Enabling Blanking](procedure-to-enable-ad-avail-blanking.md)\. 

**Restriction Flags with "Splice Insert"**  
If you select **Splice Insert** as the **Ad Avail** mode, then there is an assumption that the SCTE\-35 ad avail message does *not* include the two restriction flags that are described earlier in this section\. There is an assumption that every SCTE\-35 ad avail message should result in an ad avail\. 

Therefore, if you know that the input contains splice inserts \(not time signals\), you should leave both restriction fields unchecked\.