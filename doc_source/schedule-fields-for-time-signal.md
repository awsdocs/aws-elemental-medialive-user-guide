# Fields for a Time\_Signal Message<a name="schedule-fields-for-time-signal"></a>

This table shows the fields that apply for an action to insert a time\_signal SCTE\-35 message\.


| Field | Description | 
| --- | --- | 
| Action type | SCTE\-35 Time Signal\. | 
| Action name | A name for this time\_signal action\. For example, you might name time\_signal actions with a sequential number, restarting every day or every month\. | 
| Start type  | Fixed\. | 
| Date and time |  The UTC start time for the time\_signal\. The time should be at least 15 seconds later than the time that you submit the action\. Note that the time is the wall clock time, not the timecode in the input\.  | 
| Add Scte35 descriptors | Choose this button and complete the fields that appear\. The descriptors are a standard component of a time\_signal message\. | 