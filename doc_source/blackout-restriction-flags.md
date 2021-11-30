# Blackout restriction flags<a name="blackout-restriction-flags"></a>

**Restrictions in the input**

The segmentation descriptors in messages that are blackout triggers always include two types of flags\. These flags provide additional information as guidance for blackout in specific situations:
+ web\_delivery\_allowed\_flag
  + True means that there is no restriction on including the event’s content in a stream that is intended for web delivery\. There is no need to black out content in streams intended for web delivery\. 
  + False means that there is a restriction\. The content should be blacked out\. 
+ no\_regional\_blackout\_flag
  + True means that there is no restriction on including the event’s video in a stream intended for regional markets\. There is no need to black out content in streams intended for regional markets\. 
  + False means that there is a restriction\. The content should be blacked out\.

If both flags are present \(which is usually the case; it is unusual to have only one flag present\), then a “false” for one flag takes precedence over a “true” for the other flag\. Blackout should occur\.

Typically, in any message in the input only one of these flags is ever set to false, so only one restriction is ever in place\. There would typically never be both a regional delivery restriction and a web delivery restriction\. This is because if content is considered restricted for regional delivery, then it would not also be considered restricted for web delivery \(where the concept of a region makes no sense\)\.

**Representation of these flags in MediaLive**

There are two fields in MediaLive that let you control how MediaLive responds to these flags\. See [Enabling blanking](procedure-to-enable-ad-avail-blanking.md)\. Typically, you set the two fields to Follow \(the default\), to instruct MediaLive to follow the behavior implied by the value of the flag\.