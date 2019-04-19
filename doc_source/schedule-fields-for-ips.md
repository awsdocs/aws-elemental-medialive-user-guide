# Fields for an Input Switch<a name="schedule-fields-for-ips"></a>

This table shows the fields that apply for an action to switch the input\. 


| Field | Description | 
| --- | --- | 
| Action type |  Input Switch\. | 
| Action name |  A name for this input switch\.  | 
| Start type  | Fixed or Follow\. | 
| Date and time | If the Start type is Fixed, specify the date and time \(in UTC format\) that the channel must switch to this new input\. This time must be at least 30 seconds in the future\.Note that the time is the wall clock time, not the timecode in the input\. | 
| Reference action name |  If the **Start type** is **Follow**, choose the input to switch from, which is the input that precedes this new input\. The dropdown list shows all existing input switches that are file inputs\. Remember that input B can follow input A only if input A is a file input\. For information about these switching rules, see [Types of Switches—Fixed, Follow, and Follow Chains](ips-switch-types.md)\. For example, if you want to switch from input A to input B, specify input A in this field\.  | 
| Follow point | Applies only to a Follow start type\. The follow point is always End, to indicate that the switch will occur when the input in Reference action name has finished\. | 
| Input attachment | The input to switch to\. The input must already be set up as an [input attachment](creating-a-channel-step2.md) in this channel\. It can be a live input or a file input\. For example, if you want to switch from input A to input B, specify input B in this field\. | 