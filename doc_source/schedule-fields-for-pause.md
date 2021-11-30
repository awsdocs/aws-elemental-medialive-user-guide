# Fields for pause<a name="schedule-fields-for-pause"></a>

In **Schedule action settings**, complete the following fields\.


| Field | Description | 
| --- | --- | 
| Action type | Pause\. | 
| Action name | A name for the action\.  | 
|  Start type  | Fixed or Immediate\. | 
| Date and time |  If the **Start type** is **Fixed**, specify the UTC start time for the action\. The time should be at least 15 seconds in the future\. Note that the time is the wall clock time, not the timecode in the input\.  | 
| Actions | Choose Add actions, then for Pipeline id, choose the pipeline that you want to pause: PIPELINE\_0 or PIPELINE\_1\.  | 

When you choose **Create**, MediaLive adds an action to the schedule to pause the specified pipeline and to unpause any pipeline that isn't specified\. As a result, only the specified pipeline will be paused after the action is performed\.