# Step 4: Complete the General Settings<a name="creating-a-channel-step3"></a>

AWS Elemental MediaLive has several *settings* that apply globally to all outputs\. MediaLive also has *features* that are optional but that apply globally to all outputs if they are enabled\.

These settings and features apply to all outputs\. Therefore, they appear on the **General settings** page, rather than in individual output groups and outputs\. 

**To complete the general settings**

1. On the **Create channel** page, in the **Channel** section, choose **General settings**\.

1. In the **General channel settings** section, set the global settings and optional features as needed\. For information about each setting or feature, see the topics at the end of this procedure\. 

1. When you have finished working with these fields, go to the [next step](creating-a-channel-step4.md)\.

## Avail Blanking<a name="avail-blanking"></a>

Optional feature\. You can set this to blank out the output video during ad avails\. For more information, see [SCTE\-35 Message Processing](scte-35-message-processing.md)\.

## Avail Configuration<a name="scte35-handling"></a>

Optional feature\. You can modify the way that MediaLive handles SCTE\-35 ad avail messages, or you can keep the default behavior\. For information about the default behavior and how to modify that behavior, see [SCTE\-35 Message Processing](scte-35-message-processing.md) \.

## Blackout Slate<a name="blackout-slate"></a>

Optional feature\. You can black out the output video as specified by program metadata, if that metadata is present in the input\. For more information, see [SCTE\-35 Message Processing](scte-35-message-processing.md) \.

## Global Configuration<a name="global-channel-settings"></a>

Global configuration settings\. In this section, complete the first three fields as appropriate\. For details about each field, choose the **Info** link next to the field\. 

## Global Configuration \- Input Loss Behavior<a name="input-loss-behavior"></a>

Global configuration settings\. The **Input Loss Behavior** fields change how MediaLive handles input loss\. 

The behavior that you configure here applies to all the inputs attached to the channel\.

When MediaLive detects that the input has not arrived within the expected time, it repeats the previous frame for a configurable number of milliseconds \(from zero to forever\)\. When that time expires, it displays a black frame for a configurable number of milliseconds \(from zero to forever\)\. When that time expires, it switches to a specified slate or to a specified color\. When input resumes, the normal ingest continues\. 

You can change this behavior: for **Input loss behavior**, choose **Input Loss Behavior**\. The default values are shown in the fields that appear\. Change the fields as needed\. 

## Timecode Configuration<a name="timecode-config"></a>

Global configuration settings\. This section lets you specify the timecode for the output\. This timecode does not have to be the same as the timecode that you specified for the input \. The input timecode fields are used to notify MediaLive what timecode is present in the input, so that MediaLive can find it, and read it or apply it correctly\. The output timecode fields are used to specify the timecode format that MediaLive must apply to the output\.

## Logging<a name="channel-logging"></a>

Optional feature\. You can enable logging of activity on this individual channel\. For detailed information about this feature, see [Monitoring Using Amazon CloudWatch Logs](monitoring-with-logs.md)\.

To enable logging, choose a log level other than **DISABLED**\. The levels are listed from least to most verbose\. 

To disable logging, choose **DISABLED**\.