# Purpose of an input security group<a name="purpose-input-security-groups"></a>

Input security groups are used with specific *push* inputs where the upstream system for the source is on the public internet:
+ They are used for RTP inputs and RTMP push inputs that don't use a VPC\.
+ They aren't used for RTP VPC inputs, RTMP VPC push inputs, MediaConnect inputs, or Elemental Link inputs\. These inputs implement security in other ways\.

An input security group restricts access to the input\. The group prevents unauthorized third parties from pushing content from the public internet to an input and to the channel that this input is attached to\. Without the protection of this feature, any third party can push content to a MediaLive input if they know the input IP address and port\. Note that setting permissions on the account that owns the channel does not prevent this third\-party push; only an input security group prevents it\. 

You can attach an input security group to more than one input\. In other words, one input security group can serve several inputs\. 