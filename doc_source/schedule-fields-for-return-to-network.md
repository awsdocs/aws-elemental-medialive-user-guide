# Fields for a Return\-to\-Network Message<a name="schedule-fields-for-return-to-network"></a>

This table shows the fields that apply for an action to insert a return\-to\-network SCTE\-35 message\.


| Field | Description | 
| --- | --- | 
| Action type | SCTE\-35 Return to Network\. | 
| Action name | A name for this return\-to\-network action\. For example, "splice0003\_ return\_early"\. | 
|  Start type  | Fixed\. | 
| Date and time |  The UTC start time for the return\. The time should be at least 15 seconds later than the time that you submit the action\. Note that the time is the wall clock time, not the timecode in the input\.  | 
| Splice event id | The ID of the splice\_insert that the return\-to\-network should end\. You assigned this ID when you created the splice\_insert\. | 