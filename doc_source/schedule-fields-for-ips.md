# Fields for an input switch<a name="schedule-fields-for-ips"></a>

This section describes how to complete the fields for these three types of input switches:
+ A switch to a static live input 
+ A switch to a static file input 
+ A switch to a dynamic file input

## Fields for a switch to a static live input<a name="schedule-fields-ips-static-live"></a>

This table shows the fields that apply for an action to switch to a static live input\. 


| Field | Description | 
| --- | --- | 
| Action name |  A name for this input switch\.  | 
| Action type |  Input Switch\. | 
| Input attachment | The live input to switch to\. The input must already be set up as an [input attachment](creating-a-channel-step2.md) in this channel\. For example, if you want to switch from input A to input B, specify input B in this field\. | 
| Start type  | Fixed, Immediate, or Follow\. For information about start types for input prepare, see [Fixed, immediate, and follow switches](ips-switch-types.md)\. | 
| Date and time | If the Start type is Fixed, specify the date and time \(in UTC format\) that the channel must switch to this new input\. This time must be at least 30 seconds in the future\.Note that the time is the wall clock time, not the timecode in the input\. | 
| Reference action name |  If the **Start type** is **Follow**, choose the input to switch from, which is the input that precedes this new input\. The dropdown list shows all existing input switches that are file inputs\. Remember that input B can follow input A only if input A is a file input and the source end behavior for input A is *continue*\. For information about these switching rules, see [Fixed, immediate, and follow switches](ips-switch-types.md)\. For example, if you want to switch from input A to input B, specify input A in this field\.  | 
| Follow point | If the Start type is Follow, complete this field\. The follow point is always End, to indicate that the switch will occur when the input in Reference action name has finished\. | 

## Fields for a switch to a static file input<a name="schedule-fields-ips-static-file"></a>

This table shows the fields that apply for an action to switch to a static file input\. 


| Field | Description | 
| --- | --- | 
| Action name |  A name for this input switch\.  | 
| Action type |  Input Switch\. | 
| Input attachment | The file input to switch to\. The input must already be set up as an [input attachment](creating-a-channel-step2.md) in this channel\. For example, if you want to switch from input A to input B, specify input B in this field\. | 
| Input clippings settings – Enable input clipping | This field appears only for a file input that is [eligible for input clipping](input-clipping.md)\.Enable the field if you want to clip the file at the start and end, or only at the start, or only at the end\. | 
| Input clippings settings – Input timecode source |  Choose the source: Zero\-based – To set the start and end times relative to the start of the file, which is 00:00:00:00\. Embedded – To set the times based on the timecode in the file\. The file must have a timecode, otherwise the clipping instruction is ignored\.  | 
| Input clippings settings – Start timecode, Stop timecode |  Complete one or both fields\. Enter values in the format hh:mm:ss:ff\.  | 
| Input clippings settings – Last frame clipping behavior | This field appears only if you specify a stop timecode\. Exclude last frame – Clip the file before the frame specified in the end timecode\. For example, if the end timecode is 01:00:30:19, don't include frame 19\.Include last frame – Don't clip the file\. In the preceding example, include frame 19\. | 
| Start type  | Fixed, Immediate, or Follow\. For information about start types for input prepare, see [Fixed, immediate, and follow switches](ips-switch-types.md)\. | 
| Date and time | If the Start type is Fixed, specify the date and time \(in UTC format\) that the channel must switch to this new input\. This time must be at least 30 seconds in the future\.Note that the time is the wall clock time, not the timecode in the input\. | 
| Reference action name |  If the **Start type** is **Follow**, choose the input to switch from, which is the input that precedes this new input\. The dropdown list shows all existing input switches that are file inputs\. Remember that input B can follow input A only if input A is a file input\. For information about these switching rules, see [Fixed, immediate, and follow switches](ips-switch-types.md)\. For example, if you want to switch from input A to input B, specify input A in this field\.  | 
| Follow point | If the Start type is Follow, complete this field\. The follow point is always End, to indicate that the switch will occur when the input in Reference action name has finished\. | 

## Fields for a switch to a dynamic file input<a name="schedule-fields-ips-static-dynamic"></a>

This table shows the fields that apply for an action to switch to a dynamic file input\. 


| Field | Description | 
| --- | --- | 
| Action name |  A name for this input switch\.  | 
| Action type |  Input Switch\. | 
| Input attachment | The file input to switch to\. The input must already be set up as an [input attachment](creating-a-channel-step2.md) in this channel\.For example, if you want to switch from input A to input B, specify input B in this field\. | 
| Dynamic input setting – URL path for input source A | This field appears if the input is set up as a [dynamic input](dynamic-inputs.md)\. Enter a value to replace the $urlPath$ portion of the URL for source A in the input\. A hint below the fields shows the URL path that you created for this source\. | 
| Dynamic input setting – Use the same URL path for input source B | This field appears if the input is attached to a standard channel, meaning that it has two pipelines and therefore has two sources\.Enable this field \(the default\) if you want to use the same value for the `$urlPath$` in source A and source B\.Disable this field to use a different value, then enter the value\. | 
| Input clippings settings – Enable input clipping | This field appears only for a file input\.Enable the field if you want to clip the file at the start and end, or only at the start, or only at the end\. | 
| Input clippings settings – Input timecode source |  Choose the source: Zero\-based – To set the start and end times relative to the start of the file, which is 00:00:00:00\. Embedded – To set the times based on the timecode in the file\. The file must have a timecode, otherwise the clipping instruction is ignored\.  | 
| Input clippings settings – Start timecode, Stop timecode |  Complete one or both fields\. Enter values in the format hh:mm:ss:ff\.  | 
| Input clippings settings – Last frame clipping behavior | This field appears only if you specify a stop timecode\. Exclude last frame – Clip the file before the frame specified in the end timecode\. For example, if the end timecode is 01:00:30:19, don't include frame 19\.Include last frame – Don't clip the file\. In the preceding example, include frame 19\. | 
| Start type  | Fixed, Immediate, or Follow\. For information about start types for input prepare, see [Fixed, immediate, and follow switches](ips-switch-types.md)\. | 
| Date and time | If the Start type is Fixed, specify the date and time \(in UTC format\) when the channel must switch to this new input\. This time must be at least 30 seconds in the future\.Note that the time is the wall clock time, not the timecode in the input\. | 
| Reference action name |  If the **Start type** is **Follow**, choose the input to switch from, which is the input that precedes this new input\. The dropdown list shows all existing input switches that are file inputs\. Remember that input B can follow input A only if input A is a file input\. For information about these switching rules, see [Fixed, immediate, and follow switches](ips-switch-types.md)\. For example, if you want to switch from input A to input B, specify input A in this field\.  | 
| Follow point | If the Start type is Follow, complete this field\. The follow point is always End, to indicate that the switch will occur when the input in Reference action name has finished\. | 