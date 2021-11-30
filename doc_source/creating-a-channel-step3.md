# Step 4: Complete the general settings<a name="creating-a-channel-step3"></a>

AWS Elemental MediaLive has several *settings* that apply globally to all outputs\. MediaLive also has *features* that are optional but that apply globally to all outputs if they are enabled\.

These settings and features apply to all outputs\. Therefore, they appear on the **General settings** page, rather than in individual output groups and outputs\. 

**To complete the general settings**

1. On the **Create channel** page, in the **Channel** section, choose **General settings**\.

1. In the **General channel settings** section, set the global settings and optional features as needed\. For information about each setting or feature, see the topics at the end of this procedure\. 

1. When you have finished working with these fields, go to the [next step](creating-a-channel-step4.md)\.

## Avail blanking<a name="avail-blanking"></a>

Optional feature\. You can set this to blank out the output video during ad avails\. For more information, see [SCTE\-35 message processing](scte-35-message-processing.md)\.

## Avail configuration<a name="scte35-handling"></a>

Optional feature\. You can modify the way that MediaLive handles SCTE\-35 ad avail messages, or you can keep the default behavior\. For information about the default behavior and how to modify that behavior, see [SCTE\-35 message processing](scte-35-message-processing.md)\.

## Blackout slate<a name="blackout-slate"></a>

Optional feature\. You can black out the output video as specified by program metadata, if that metadata is present in the input\. For more information, see [SCTE\-35 message processing](scte-35-message-processing.md)\.

## Feature activations<a name="channel-gen-feature-activ"></a>

Optional features\. You can enable the input prepare feature for input switching\. For more information, see [Preparing inputs in AWS Elemental MediaLive](feature-prepare-input.md)\. 

## Global configuration<a name="global-channel-settings"></a>

Global configuration settings\. In this section, complete the first three fields as appropriate\. For details about each field, choose the **Info** link next to the field\. 

## Global configuration \- Input loss behavior<a name="input-loss-behavior"></a>

Global configuration settings\. The **Input Loss Behavior** fields change how MediaLive handles input loss\. 

The behavior that you configure here applies to all the inputs attached to the channel\.

When MediaLive detects that the input has not arrived within the expected time, it repeats the previous frame for a configurable number of milliseconds \(from zero to forever\)\. When that time expires, it displays a black frame for a configurable number of milliseconds \(from zero to forever\)\. When that time expires, it switches to a specified slate or to a specified color\. When input resumes, the normal ingest continues\. 

You can change this behavior: for **Input loss behavior**, choose **Input Loss Behavior**\. The default values are shown in the fields that appear\. Change the fields as needed\. 

## Motion graphics configuration<a name="channel-config-mgi"></a>

Optional feature\. You can enable the motion graphics overlay feature\. For more information, see [Working with motion graphics overlays](feature-mgi.md)\. 

## Nielsen configuration<a name="nielsen-configuration"></a>

Optional feature\. You can configure a MediaLive channel to convert Nielsen watermarks to ID3 metadata\. For more information see [Converting Nielsen watermarks to ID3](feature-nielsen-id3.md)\.

## Timecode configuration<a name="timecode-config"></a>

Global configuration settings\. This section lets you specify the timecode for the output\. For more information about configuring the timecode, see [Timecode configuration](timecode.md)\.

## Logging<a name="channel-logging"></a>

Optional feature\. You can enable logging of activity on this individual channel\. For detailed information about this feature, see [Monitoring a channel using Amazon CloudWatch Logs](monitoring-with-logs.md)\.

To enable logging, choose a log level other than **DISABLED**\. The levels are listed from least to most verbose\. 

To disable logging, choose **DISABLED**\.