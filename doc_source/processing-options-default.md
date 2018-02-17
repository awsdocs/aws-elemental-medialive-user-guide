# Processing Features – Default Behavior<a name="processing-options-default"></a>

The default handling of SCTE\-35 by AWS Elemental MediaLive is the following:

+ No passthrough – Do not pass through SCTE\-35 messages in any data stream outputs\. 

+ No blanking or blackout – Do not blank out video content for any events\. Leave the content as is\.

+ No manifest decoration – Do not convert any SCTE\-35 messages to event information in any output manifests or data streams\.

If this is the desired behavior, you do not need to read any further in this SCTE\-35 section\.