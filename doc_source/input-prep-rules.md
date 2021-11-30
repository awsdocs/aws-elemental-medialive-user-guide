# Rules and limits for input prepare<a name="input-prep-rules"></a>

**One active prepare at a time**  
The schedule can contain any number of input prepare actions, but only one input prepare action can be active at one time\. 

**Start time at least 10 seconds in advance**  
Set up each input prepare action so that it starts at least 10 seconds before the associated switch\.

**No RTMP pull inputs**  
A channel cannot have both RTMP pull input and the input prepare feature enabled\. \(RTMP push inputs are acceptable\.\) You must choose which feature is more important—the input prepare or the RTMP pull input\. 
+ If you want to use the input prepare feature and the channel already has an RTMP pull input, you must first remove the input\.
+ If you want to add an RTMP pull input and the channel already has input prepare actions in the schedule, see [Enabling and disabling the input prepare feature](input-prep-enable.md)\.