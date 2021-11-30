# Enabling and disabling the input prepare feature<a name="input-prep-enable"></a>

Before you add input prepare actions to the schedule, you must enable the feature\.

**To enable the feature**
+ On the **Create channel** page, in **General settings**, in the **Feature activations** section, set **Input prepare schedule actions **to **Enabled**\. 

**To disable the feature**

You can disable the input prepare feature\. 

Typically, the only reason to disable input prepare is because you must [attach an RTMP pull input ](input-prep-rules.md)to the channel\. 

1. Stop the channel\. 

1. [Delete ](schedule-using-console-delete.md)all active and future input prepare actions from the schedule\. You don't need to delete stale input prepare actions from the schedule\.

1. On the **Create channel** page, in **General settings**, in the **Feature activation** section, set **Input prepare schedule actions **to **Disabled**\. 

1. Attach the [RTMP pull input](creating-a-channel-step2.md) in the usual way\.

**Topics**