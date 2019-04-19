# Rules and Limits for Input Switches<a name="ips-limits"></a>

This section describes the rules and limits that apply to input switches\.

## Rules for Types of Inputs<a name="ips-rules-input-type"></a>

There are three restrictions on the different input types that can be in the "pool" of inputs attached to one channel:
+ You can't have both MediaConnect inputs and VPC inputs attached to one channel\.
+ You can have multiple MediaConnect inputs attached to one channel, but all those inputs must be in the same two Availability Zones\. 
+ You can have multiple VPC inputs attached to one channel, including both RTP VPC inputs and RTMP VPC push inputs\. But all those inputs must be in the same two Availability Zones\.

For example:
+ You can have both HLS inputs and MediaConnect inputs attached to one channel\. 
+ You can have both RTMP push inputs used for a source from the public internet and an RTMP VPC push input\.

## Limit to Inputs in a Channel<a name="ips-limits-inputs-per-channel"></a>

Each channel that will implement input switching can contain a specific number of inputs, as follows: 
+ A maximum 20 inputs\. 
+ From 0 to 2 of those inputs can be live inputs\. 
+ The remainder of the 20 inputs can be file inputs\. File inputs are file\-based video inputs\.

## No Limits to the Number of Input Switches<a name="no-limits-switches"></a>

The schedule for the channel can contain any number of scheduled input switching actions\. 

You can switch to a specific input as many times as you want\. 

## Reusing a File Input<a name="ips-file-input-rule"></a>

If you switch away from a file input and then switch back to it, the channel ingests the file from the start of the file\. This rule applies even if you had switched away from the file input before the end of the file\. 