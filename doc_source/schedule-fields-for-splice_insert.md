# Fields for a splice\_insert message<a name="schedule-fields-for-splice_insert"></a>

This table shows the fields that apply for an action to insert a splice\_insert SCTE\-35 message\. 


| Field | Description | 
| --- | --- | 
| Action type | SCTE\-35 Splice Insert\. | 
| Action name | A name for this splice\_insert action\. For example, splice\_insert actions could be numbered sequentially, restarting every day or every month\.  | 
| Start type  | Fixed or Follow or Immediate\.  | 
| Date and time |  If the **Start type** is **Fixed**, specify the UTC start time for the splice\_insert action\. The time should be at least 15 seconds in the future\. Note that the time is the wall clock time, not the timecode in the input\.  | 
| Reference action name |  If the **Start type** is **Follow**, choose the input to follow\. The dropdown list shows all existing input switches that are file inputs\. Remember that a SCTE\-35 action can follow input A only if input A is a file input and the source end behavior for input A is *continue*\. For information about these switching rules, see [Fixed, immediate, and follow switches](ips-switch-types.md)\.  | 
| Follow point | If the Start type is Follow, complete this field\. The follow point is always End, to indicate that the switch will occur when the input in Reference action name has finished\. | 
| Splice event id | The ID for the splice event\. Enter an ID for the splice event that is unique among all scheduled and active splice\_insert messages in this channel\. A message is active if the schedule action is in process in the channel and has not completed\.  | 
| Duration | The duration for the splice event\. Complete in one of these ways:[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/schedule-fields-for-splice_insert.html) | 

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