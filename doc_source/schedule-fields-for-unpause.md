# Fields for unpause<a name="schedule-fields-for-unpause"></a>

In **Schedule action settings**, complete the following fields\.


| Field | Description | 
| --- | --- | 
| Action type | Pause\. | 
| Action name | A name for the action\.  | 
|  Start type  | Fixed or Immediate\. | 
| Date and time |  If the **Start type** is **Fixed**, specify the UTC start time for the action\. The time should be at least 15 seconds in the future\. Note that the time is the wall clock time, not the timecode in the input\.  | 
| Actions | Keep this section empty\. Don't add any actions\.  | 

When you choose **Create**, the empty **Actions** section instructs MediaLive to add an action to the schedule to unpause all pipelines\.