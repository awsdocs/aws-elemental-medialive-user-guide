# Ad avail blanking restriction flags<a name="ad-avail-blanking-restriction-flags"></a>

**Restrictions in the input**

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

If both flags are present \(which is usually the case with time\_signal; it is unusual to have only one flag present\), then a “false” for one flag takes precedence over a “true” for the other flag\. Blanking should occur\.

Typically, in any message in the input only one of these flags is ever set to false, so only one restriction is ever in place\. There would typically never be *both* a regional delivery restriction and a web delivery restriction\. This is because if content is considered restricted for regional delivery, then it would not also be considered restricted for web delivery \(where the concept of a region makes no sense\)\.

**Representation of these Restrictions in MediaLive**

There are two fields in MediaLive that let you control how MediaLive responds to the these flags\. See [Enabling blanking](procedure-to-enable-ad-avail-blanking.md)\. Typically, you set the two fields to Follow \(the default\), to instruct MediaLive to follow the behavior implied by the value of the flag\.