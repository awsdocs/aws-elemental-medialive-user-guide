# Monitoring a multiplex using the MediaLive Console<a name="monitoring-multiplex-console"></a>

You can view the activity of your multiplex and its current state\.

**To monitor activity on a multiplex \(MediaLive console\)**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Multiplexes**\.

1. The **Multiplexes** page shows a list of your multiplexes\. Each line in the list provides basic information about the multiplex, including its state:
   + **Creating**
   + **Deleting**
   + **Idle**: The multiplex isn't running\. For information about charges that you accrue when a multiplex is idle, see [Pricing](pricing.md)\.
   + **Recovering**: One or both pipelines in the multiplex failed, but MediaLive is restarting it\. 
   + **Running**
   + **Starting**
   + **Stopping**
   + 

   Note that [Amazon CloudWatch events](monitoring-via-cloudwatch.md) also capture these state changes\.

1. To view more details about a multiplex, choose the name of that multiplex\. The **Multiplex details** page appears\.

## Viewing status information<a name="view-status-info"></a>

The **Multiplex details** page is divided into two panes\. The second pane is divided into tabs\.

### Details tab<a name="multiplex-details-tab"></a>

The **Details** tab shows the fields that you set when you created the multiplex\. 

It also shows this information that MediaLive assigns:
+ The ARN of the multiplex\.
+ The ARNs of the two entitlements that MediaLive automatically creates when you create the multiplex\. For more information about these entitlements, see [Starting the multiplex](start-multiplex.md)\.

### Programs tab<a name="multiplex-programs-tab"></a>

The **Programs** tab lists the tabs that are in the multiplex\. For information about programs, see [Overview of multiplex and MPTS in AWS Elemental MediaLive](mpts-general.md)\.

### Bandwidth monitoring tab<a name="multplex-bandwidth-tab"></a>

The **Bandwidth monitoring **tab shows information about the bandwidth allocation for the multiplex\. 

**To display the information as a bar chart**

1. Choose **Bar chart**\. 

1. Choose to show the multiplex \(all the programs in the multiplex\) or a specific program\.

1. Choose which pipeline to show\.

The chart always shows the data for the most recent minute\. The chart refreshes every minute\.

**To display the information as an area chart**

1. Choose **Area chart**\.

1. Set the time window\. This window sets the size of the x\-axis\. The window always shows 60 data points\. Therefore, a window of 1 hour shows a data point every minute, for example\. A window of 1 day shows a data point every 24 minutes\.

1. Choose to show the multiplex \(all the programs in the multiplex\) or a specific program\.

1. Choose which pipeline to show\.

### Alerts tab<a name="multiplex-alerts-tab"></a>

MediaLive generates alerts for a multiplex when an issue or potential issue occurs in either pipeline in a multiplex\. These alerts are displayed in two ways:
+ On the right side of the **Status** pane, there is a count of active alerts for each pipeline\. 
+ On the **Alerts** tab, details about each alert are displayed\. 

If an alert is still active, the **Cleared** column is blank\. If an alert has cleared, the column shows the timestamp for when it cleared\.

**To handle an alert**

1. When an alert occurs, look at the **Alerts** tab to determine possible causes of the issue\. Take steps to resolve the issue\. 

   After you resolve the issue, MediaLive automatically clears the alert\. The **Cleared** column shows the timestamp for when it cleared\.

1. If you stop a channel, alerts always automatically clear\.

### Tags Tab<a name="multiplex-tags-tab"></a>

For information about tags, see [Tagging AWS Elemental MediaLive resources](tagging.md)\. 