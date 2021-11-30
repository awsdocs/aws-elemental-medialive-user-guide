# Fields for activating a motion graphics overlay<a name="schedule-fields-for-mg"></a>

This table shows the fields that apply for an action to activate a motion graphics overlay\. 


| Field | Description | 
| --- | --- | 
| Action type | Motion Graphics Activate\. | 
| Action name | A name for this activation action\. For example, the name of the motion graphic asset\.  | 
| Start type  | Fixed or Immediate\. | 
| Date and time |  The date and time \(in UTC format\) that the channel must activate the motion graphics overlay\. The time should be at least 60 seconds later than the time that you submit the action\.  Note that the time is the wall clock time, not the timecode in the input\.  | 
| Duration | Optional\. The duration in milliseconds for the motion graphic to remain on the video\. If you omit this field or set it to 0, the duration is unlimited and the motion graphic will remain until you create a deactivate action\. | 
| URL | The URL of the motion graphics asset\. This asset is always an HTML file\. The URL follows this syntax:`<protocol>://<path>/<file>.html`For example:`https://example.com/ticker_tape.html` | 
| Credentials |  Complete this section only if the server where the motion graphics asset is stored requires user authentication from MediaLive\. Enter the user name provided by the owner of the server\. For the password, enter the name of the password stored on the AWS Systems Manager Parameter Store\. Don't enter the password itself\. For more information, see [Requirements for AWS Systems Manager—creating password parameters in parameter store ](requirements-for-EC2.md)\.  | 