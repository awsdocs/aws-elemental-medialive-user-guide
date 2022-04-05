# Setting maintenance windows<a name="setting-maintenance"></a>

You can select the day and time that recurring maintenance events will occur\. This is called a *maintenance window* and is used every time a maintenance event is required\. These windows help to ensure that maintenance has minimal impact to your production\. If you need to change the day and time, you can edit the maintenance window\.

When a channel requires maintenance, you can select a specific date for the maintenance to occur\. This date must be before the **Required by** date\.

If you do not set a maintenance window, you must stop and restart the channel manually\. If you do not perform either of those actions, AWS sets a maintenance window for you, automatically\. We recommend you set a maintenance window for each channel that requires maintenance\.

**To set a maintenance window**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channels**\. Channels requiring maintenance will display **Required** under the **Maintenance window** column\.

1. Select the channel or channels\. A unique maintenance window can be set for each channel\. Alternately, selecting the upper\-most check box in the channel selection column will select all channels\.

1. Under the **Channel actions** dropdown menu, select **Edit channel maintenance window**\.

1. Select a **Start day** and **Start hour** for maintenance to occur\. Time is presented in UTC\.

1. If maintenance is required on the channel, you can select a specific date for the maintenance to occur\.
   + In the **Upcoming maintenance** section, expand **Additional maintenance settings**\.
   + Use the **Maintenance window date** selector to choose a date before the **Required by date**\.

1. Verify your selections are correct and choose **Save**\.

The selected **Start day** and **Start hour** is used for all future recurring maintenance events\. The selected **Maintenance window date** is used for the next maintenance, only\. After the maintenance is complete, the **Maintenance status** column on the **Channels dashboard** will display **Not required**\.