# Enabling Channel Logs<a name="enabling-disabling-logs"></a>

You enable the capture of logging information for an individual channel on the MediaLive console\. You enable logging and set the logging level \(error, warning, info, or debug\) on a per channel basis\. The channel must be idle in order to enable or disable logging\. 

**To enable a channel log \(MediaLive console\)**

1. If you are a returning user of MediaLive, check with your administrator that your deployment has been set up in AWS IAM to support channel logs\.

1. Your administrator might instruct you to update the `MediaLiveAccessRole` permission in one of the channels\. If you are given this instruction, you must [edit a channel](editing-deleting-channel.md#editing-a-channel) \(choose any idle channel\), [display the **Channel and input details** page](role-and-remember-arn.md), and choose the **Update** button\. When the role is updated in one channel, the change applies to all channels\. 

1. To enable logging in a new channel, set up logging during [creation](creating-channel-scratch.md)\. To enable logging in an existing channel, [edit the channel](editing-deleting-channel.md#editing-a-channel); this channel must be idle\. In both cases, on the **General settings** page, in the **Channel logging** section, choose **Logging**\. Choose a level other than **DISABLED**\. For more information, see [Logging](creating-a-channel-step3.md#channel-logging)\.

1. You or an administrator can also go into CloudWatch Logs and set an expiry date for the logs\.

## Disabling Channel Logs<a name="disabling-logs"></a>

You disable the capture of logging information for an individual channel on the MediaLive console\. Edit the channel, and on the **General settings** page, on the **Channel logging** section, choose **Logging**\. Set the level to **DISABLED**\. 