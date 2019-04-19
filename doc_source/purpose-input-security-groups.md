# Purpose of an Input Security Group<a name="purpose-input-security-groups"></a>

Input security groups are used with specific "push" inputs where the upstream system for the source is on the public internet:
+ They are used for RTP inputs and RTMP push inputs that don't use a VPC\.
+ They aren't used for RTP VPC inputs, RTMP VPC push inputs, or MediaConnect inputs\. These inputs implement security in other ways\.

For the relevant push inputs, an input security group restricts access to the input and prevents unauthorized third parties from pushing content into a channel that is associated with that input\. Without the protection of this feature, any third party could push content to an MediaLive input if they know the IP address and port\. Note that setting permissions on the account that owns the channel does not prevent this third\-party push; only an input security group prevents it\. 

You can attach an input security group to more than one input; one input security group can "serve" several inputs\. 