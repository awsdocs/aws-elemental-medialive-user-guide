# Fields for a time\_signal message<a name="schedule-fields-for-time-signal"></a>

This table shows the fields that apply for an action to insert a time\_signal SCTE\-35 message\.


| Field | Description | 
| --- | --- | 
| Action type | SCTE\-35 Time Signal\. | 
| Action name | A name for this time\_signal action\. For example, you might name time\_signal actions with a sequential number, restarting every day or every month\. | 
| Start type  | Fixed or Follow or Immediate\. | 
| Date and time |  If the **Start type** is **Fixed**, specify the UTC start time for the time\_signal\. The time should be at least 15 seconds in the future\. Note that the time is the wall clock time, not the timecode in the input\.  | 
| Reference action name |  If the **Start type** is **Follow**, choose the input to follow\. The dropdown list shows all existing input switches that are file inputs\. Remember that a SCTE\-35 action can follow input A only if input A is a file input and the source end behavior for input A is *continue*\. For information about these switching rules, see [Fixed, immediate, and follow switches](ips-switch-types.md)\.  | 
| Follow point | If the Start type is Follow, complete this field\. The follow point is always End, to indicate that the switch will occur when the input in Reference action name has finished\. | 
| Add Scte35 descriptors | Choose this button and complete the fields that appear\. The descriptors are a standard component of a time\_signal message\. | 