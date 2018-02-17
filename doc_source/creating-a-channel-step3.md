# Step 3: Set Global Settings and Optional Features<a name="creating-a-channel-step3"></a>

AWS Elemental MediaLive has several *settings* that apply globally to all outputs; these settings are therefore located in this section, rather than in individual output groups and outputs\.

AWS Elemental MediaLive also has *features* that are optional but that apply globally if they are enabled\. 

1. On the Create channel navigation pane, choose General Settings\.

1. Set these optional features and global settings as needed\. See below for details on the groups of settings\.

1. When done with these fields, go to the next step\.

## Avail Blanking<a name="avail-blanking"></a>

Optional feature\. You can set up to blank out the output video during ad avails\. For details, see [[ERROR] BAD/MISSING LINK TEXT](scte-35-message-processing.md)\.

## Avail Configuration<a name="scte35-handling"></a>

Optional feature\. You can modify the way that AWS Elemental MediaLive handles SCTE\-35ad avail messages, or you can leave the default behavior\. See [[ERROR] BAD/MISSING LINK TEXT](scte-35-message-processing.md) for information on the default behavior and modifying that behavior\.

## Blackout Slate<a name="blackout-slate"></a>

Optional feature\. You can set up to black out the output video as specified by program metadata, if that metadata is present in the input\. For details, see [[ERROR] BAD/MISSING LINK TEXT](scte-35-message-processing.md) \.

## Global Configuration<a name="global-channel-settings"></a>

Global configuration settings\. In this section, complete the first three fields as appropriate\. For details on each field, choose the Info link next to the field\. 

## Global Configuration \- Input Loss Behavior<a name="input-loss-behavior"></a>

Global configuration settings\. The Input Loss Behavior fields change how AWS Elemental MediaLive handles input loss\. When AWS Elemental MediaLive detects that the input has not arrived within the expected time, it repeats the previous frame for a configurable number of milliseconds \(from zero to forever\)\. When that time expires, it displays a black frame for a configurable number of milliseconds \(from zero to forever\)\. When that time expires, it switches to a specified slate or to a specified color\. When input resumes, the normal ingest continues\. 

You can change this behavior: in Input Loss Behavior, choose Input Loss Behavior\. The default values are shown in the fields that appear\. Change the fields as desired\. If you want to later switch back to the default behavior, simply set Input Loss Behavior to Disabled\.

## Image Inserter<a name="image-inserter"></a>

Optional feature\. You can insert static graphic overlays on the output video\. 

## Timecode Config<a name="timecode-config"></a>

Global configuration settings\. This section lets you specify the timecode for the output\. This timecode does not have to be the same as the timecode you specified for the input \. The input timecode fields are used to notify AWS Elemental MediaLive what timecode is present in the input, so that AWS Elemental MediaLive can find it, and read it or apply it correctly\. The output timecode fields are used to specify the timecode format AWS Elemental MediaLive must apply to the output\.

