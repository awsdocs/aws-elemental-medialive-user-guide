# Rules and limits for input switches<a name="ips-limits"></a>

This section describes the rules and limits that apply to input switches\.

## Rules for types of inputs<a name="ips-rules-input-type"></a>

There is flexibility in the number and types of inputs that you can set up for input switching\. For example:
+ You can have both HLS live inputs and MediaConnect inputs attached to one channel\. 
+ You can have both RTMP push inputs used for a source from the public internet and an RTMP VPC push input\.

But there are also some restrictions:
+ The number of push inputs and pull inputs that you can attach to a channel\.
+ The number of inputs of a specific input type\. For example, the number of CDI inputs you can attach to a channel\.
+ Use of VOD assets\.
+ Use of inputs in different Availability Zones\.
+ Use of dynamic inputs in an input switching workflow\.

For detailed information about these rules, see [AWS Elemental MediaLive feature rules and limits](eml-limitations-and-rules.md)\.

## First switch must be static<a name="rule-first-switch"></a>

The first switch in the channel must be for a static input\. It can't be a dynamic input\. 

## No limits to the number of input switches<a name="no-limits-switches"></a>

The schedule for the channel can contain any number of scheduled input switching actions\. 

You can switch to a specific input as many times as you want\. 

## Reusing a file input<a name="ips-file-input-rule"></a>

If you switch away from a static file input and then switch back to it, the channel ingests the file from the start of the file or start of the file clip \(if you clipped the file\)\. This rule applies even if you switch away from the file input before the end of the file\. 

This rule also applies if you switch away from a dynamic file input and then switch back to it without changing the value of the variable portion of the URL\. The channel always ingests from the start\.