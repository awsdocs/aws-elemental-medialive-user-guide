# Fields for an input prepare<a name="schedule-fields-for-input-prep"></a>

This section describes how to complete the fields for these three types of input prepares:
+ A prepare of a static live input 
+ A prepare of a static file input 
+ A prepare of a dynamic file input

## Fields for a prepare of a static live input<a name="sched-fields-prep-static-live"></a>

This table shows the fields that apply for an action to prepare a static live input\. 


| Field | Description | 
| --- | --- | 
| Action name |  A name for this input prepare\.  | 
| Action type |  Input Prepare\. | 
| Input attachment | The live input to prepare\. The input must already be set up as an [input attachment](creating-a-channel-step2.md) in this channel\. | 
| Start type  | Fixed, Immediate, or Follow\. For information about start types for input prepare, see [Types of starts for input prepares](plan-prep-start-types.md)\. | 
| Date and time | If the Start type is Fixed, specify the date and time \(in UTC format\) that the channel must start to prepare the input\. This time should be at least 10 seconds before the upcoming input switch\.Note that the time is the wall clock time, not the timecode in the input\. | 
| Reference action name |  If the **Start type** is **Follow**, choose the input to follow\. This input is the input whose end you want to use as the trigger for the input prepare\. It is not the input for the upcoming input switch\. The dropdown list shows all existing input switches\. If the input switch that you want to use as the reference \(trigger\) isn't listed, you need to first create that input switch\. For information about start types for input prepare, see [Types of starts for input prepares](plan-prep-start-types.md)\.  | 
| Follow point | If the Start type is Follow, complete this field\. The follow point is always End, to indicate that the input prepare will occur when the input in Reference action name has finished\. | 

## Fields for a prepare of a static file input<a name="sched-fields-prep-static-file"></a>

This table shows the fields that apply for an action to prepare a static file input\. 


| Field | Description | 
| --- | --- | 
| Action name |  A name for this input prepare\.  | 
| Action type |  Input Prepare\. | 
| Input attachment | The file input to prepare\. The input must already be set up as an [input attachment](creating-a-channel-step2.md) in this channel\. | 
| Input clippings settings – Enable input clipping | This field appears only for a file input that is [eligible for input clipping](input-clipping.md)\.Enable the field if the upcoming input switch \(which you are preparing\) will also be clipped\. You must set up the prepare action with identical clipping instructions as the switch action\. | 
| Input clippings settings – Input timecode source |  Choose the source: Zero\-based – To set the start and end times relative to the start of the file, which is 00:00:00:00\. Embedded – To set the times based on the timecode in the file\. The file must have a timecode, otherwise the clipping instruction is ignored\. Make sure you choose the same source in this prepare action and the upcoming switch action\.  | 
| Input clippings settings – Start timecode, Stop timecode |  Complete one or both fields\. Enter values in the format hh:mm:ss:ff\. Make sure you enter the same values in this prepare action and the upcoming switch action\.  | 
| Input clippings settings – Last frame clipping behavior | This field appears only if you specify a stop timecode\. Exclude last frame – Clip the file before the frame specified in the end timecode\. For example, if the end timecode is 01:00:30:19, don't include frame 19\.Include last frame – Don't clip the file\. In the preceding example, include frame 19\.Make sure you choose the same option in this prepare action and the upcoming switch action\. | 
| Start type  | Fixed, Immediate, or Follow\. For information about start types for input prepare, see [Types of starts for input prepares](plan-prep-start-types.md)\. | 
| Date and time | If the Start type is Fixed, specify the date and time \(in UTC format\) that the channel must start to prepare this input\. This time should be at least 10 seconds before the upcoming input switch\.Note that the time is the wall clock time, not the timecode in the input\. | 
| Reference action name |  If the **Start type** is **Follow**, choose the input to follow\. This input is the input whose end you want to use as the trigger for the input prepare\. It is not the input for the upcoming input switch\. The dropdown list shows all existing input switches\. If the input switch that you want to use as the reference \(trigger\) isn't listed, you need to first create that input switch\. For information about start types for input prepare, see [Types of starts for input prepares](plan-prep-start-types.md)\.  | 
| Follow point | If the Start type is Follow, complete this field\. The follow point is always End, to indicate that the input prepare will occur when the input in Reference action name has finished\. | 

## Fields for a prepare of a dynamic file input<a name="sched-fields-prep-static-dynamic"></a>

This table shows the fields that apply for an action to prepare a dynamic file input\. 


| Field | Description | 
| --- | --- | 
| Action name |  A name for this input prepare\.  | 
| Action type |  Input Prepare\. | 
| Input attachment | The file input to prepare\. The input must already be set up as an [input attachment](creating-a-channel-step2.md) in this channel\. | 
| Dynamic input setting – URL path for input source A | This field appears if the input is set up as a [dynamic input](dynamic-inputs.md)\. Enter a value to replace the `$urlPath$` portion of the URL for source A in the input\. A hint below the fields shows the URL path that you created for this source\.Make sure you enter the same values in this prepare action and the upcoming switch action\. | 
| Dynamic input setting – Use the same URL path for input source B | This field appears if the input is attached to a standard channel, meaning that it has two pipelines and therefore has two sources\.Enable this field \(the default\) if you want to use the same value for the `$urlPath$` in source A and source B\.Disable this field to use a different value, then enter the value\.Make sure you choose the same option in this prepare action and the upcoming switch action\. | 
| Input clippings settings – Enable input clipping | This field appears only for a file input that is [eligible for input clipping](input-clipping.md)\.Enable the field if the upcoming input switch \(which you are preparing\) will also be clipped\. You must set up the prepare action with identical clipping instructions as the switch action\. | 
| Input clippings settings – Input timecode source |  Choose the source: Zero\-based – To set the start and end times relative to the start of the file, which is 00:00:00:00\. Embedded – To set the times based on the timecode in the file\. The file must have a timecode, otherwise the clipping instruction is ignored\. Make sure you choose the same source in this prepare action and the upcoming switch action\.  | 
| Input clippings settings – Start timecode, Stop timecode |  Complete one or both fields\. Enter values in the format hh:mm:ss:ff\. Make sure you enter the same values in this prepare action and the upcoming switch action\.  | 
| Input clippings settings – Last frame clipping behavior | This field appears only if you specify a stop timecode\. Exclude last frame – Clip the file before the frame specified in the end timecode\. For example, if the end timecode is 01:00:30:19, don't include frame 19\.Include last frame – Don't clip the file\. In the preceding example, include frame 19\.Make sure you choose the same option in this prepare action and the upcoming switch action\. | 
| Start type  | Fixed, Immediate, or Follow\. For information about start types for input prepare, see [Types of starts for input prepares](plan-prep-start-types.md)\. | 
| Date and time | If the Start type is Fixed, specify the date and time \(in UTC format\) that the channel must start to prepare this input\. This time should be at least 10 seconds before the upcoming input switch\.Note that the time is the wall clock time, not the timecode in the input\. | 
| Reference action name |  If the **Start type** is **Follow**, choose the input to follow\. This input is the input whose end you want to use as the trigger for the input prepare\. It is not the input for the upcoming input switch\. The dropdown list shows all existing input switches\. If the input switch that you want to use as the reference \(trigger\) isn't listed, you need to first create that input switch\.  | 
| Follow point | If the Start type is Follow, complete this field\. The follow point is always End, to indicate that the input prepare will occur when the input in Reference action name has finished\. | 