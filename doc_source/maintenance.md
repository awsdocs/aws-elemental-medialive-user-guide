# Maintenance windows<a name="maintenance"></a>

AWS Elemental MediaLive routinely performs maintenance on underlying systems for security, reliability, and operational performance\. The maintenance activities include actions such as patching the operating system, updating drivers, or installing software and patches\.

**Note**  
 As part of the maintenance process, your channel must be restarted\.

 You can select the day and time that maintenance events occur\. This is called a *maintenance window* and is used every time a maintenance event is required\. If you need to change the day and time, you can edit the maintenance window\.

When a maintenance event occurs, AWS will assign your channel a **Required by** date\. If you do not have a maintenance window set up to restart the channel, see [Setting maintenance windows](setting-maintenance.md)\. To view the channels that require maintenance, use the MediaLive console or AWS Health Events in your Personal Health Dashboard, see [Viewing channels that require maintenance](viewing-maintenance.md)\.

If you do not set a maintenance window, you must stop and restart the channel manually\. If you do not perform either of those actions, AWS sets a maintenance window for you, automatically\.

When maintenance does not occur at the scheduled date and time, MediaLive will reschedule it to occur in the following week’s maintenance window\.

**Topics**
+ [Viewing channels that require maintenance](viewing-maintenance.md)
+ [Setting maintenance windows](setting-maintenance.md)