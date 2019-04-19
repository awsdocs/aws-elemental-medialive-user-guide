# Fields for a Splice\_Insert Message<a name="schedule-fields-for-splice_insert"></a>

This table shows the fields that apply for an action to insert a splice\_insert SCTE\-35 message\. 


| Field | Description | 
| --- | --- | 
| Action type | SCTE\-35 Splice Insert\. | 
| Action name | A name for this splice\_insert action\. For example, splice\_insert actions could be numbered sequentially, restarting every day or every month\.  | 
| Start type  | Fixed\.  | 
| Date and time |  The UTC start time for the splice\_insert action\. The time should be at least 15 seconds later than the time that you submit the action\. Note that the time is the wall clock time, not the timecode in the input\.  | 
| Splice event id | The ID for the splice event\. Enter an ID for the splice event that is unique among all scheduled and active splice\_insert messages in this channel\. A message is active if the schedule action is in process in the channel and has not completed\.  | 
| Duration | The duration for the splice event\. Enter the duration, in 90 kHz ticks\. For example, 1350000, which is equal to 15 seconds\. | 

The splice\_insert inserted in the transport stream will have the following:

```
      segmentation_event_cancel_indicator = 0 
      out_of_network = 1
      duration_flag = 1
      duration = the specified time
```

Or

```
      segmentation_event_cancel_indicator = 0
      out_of_network = 1
      duration_flag = 0
```