# Setting maintenance windows<a name="setting-maintenance"></a>

You can select the day and time that maintenance events will occur\. This is called a *maintenance window* and is used every time a maintenance event is required\. These windows help to ensure that maintenance has minimal impact to your production\. If you need to change the day and time of a maintenance window, you can use the MediaLive console to edit it\.

You can also manually restart the channels that require maintenance\. If you don't set a maintenance window, and don't restart manually, AWS sets the maintenance window\. We recommend you set a maintenance window for each channel that requires maintenance\.

**To set a maintenance window**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channels**\. Channels requiring maintenance will display **Required** under the **Maintenance window** column\.

1. Select the channel or channels\. A unique maintenance window can be set for each channel\. Alternately, selecting the upper\-most check box in the channel selection column will select all channels\.

1. Under the **Channel actions** dropdown menu, select **Edit channel maintenance window**\.

1. Select a day and time for maintenance to occur and choose **Save**\. Time is presented in UTC\.

1. You can verify the window by viewing the **Maintenance window** column on **Channels** dashboard\.

The selected day and time is used for all future recurring maintenance events\. Repeat these steps to add or edit maintenance windows\. After the maintenance is complete, the **Maintenance status** column on the **Channels dashboard** will display **Not required**\.