# Working with Input Security Groups<a name="working-with-input-security-groups"></a>

An *input security group* restricts access to an input and prevents unauthorized third parties from pushing content into a channel that is associated with a "push" input\. Input security groups are required with RTP and RTMP “push” inputs; they do not apply to “pull” inputs such as HLS\. Without the protection of this feature, any third party could push content to an AWS Elemental MediaLive input if they know the IP address and port\. Note that setting permissions on the account that owns the channel does not prevent this third\-party push; only an input security group prevents it\. 

An input security group is a set of one or more whitelist rules\. Each rule is a range of IP addresses\. These IP addresses are allowed to push traffic to the input destinations of a channel \(to push traffic to the channel’s input\)\. 

You create an input security group and attach it to an input\. 

You can attach an input security group to more than one input\. But each input can be associated with only one input security group\. In other words, the rule is one input security group to one or more inputs\. 