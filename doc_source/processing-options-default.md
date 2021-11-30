# Processing features – default behavior<a name="processing-options-default"></a>

The default handling of SCTE\-35 by MediaLive is the following:
+ No passthrough – Remove SCTE\-35 messages in any data stream outputs\. There is one exception: for MediaPackage outputs, passthrough is always enabled\.
+ No blanking or blackout – Do not blank out video content for any events\. Leave the content as is\.
+ No manifest decoration – Do not convert any SCTE\-35 messages to event information in any output manifests or data streams\. There is one exception: for MediaPackage outputs, manifest decoration is always enabled and can't be disabled\.

If this is the behavior that you want, you don't need to read any further in this SCTE\-35 section\.

Typically, you change these defaults only if you want to include ad avail information in the channel outputs\. The following are examples of when you change the defaults
+ You enable passthrough\.
+ You enable manifest decoration, if your channel includes HLS, MediaPackage, or Microsoft Smooth output groups\.
+ You blank or blackout video content depending on your agreement with the content provider\. 