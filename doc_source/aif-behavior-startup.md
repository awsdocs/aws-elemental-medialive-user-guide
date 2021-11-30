# Starting the channel<a name="aif-behavior-startup"></a>

Start the channel in the usual way\. MediaLive follows this behavior when you start the channel:
+ If the input attachment list contains only the input failover pair, MediaLive starts with the primary input, which always appears first in the attachments\.
+ If you have set up the channel to always use the schedule, even with the first input, then MediaLive starts with the first input in the schedule\. This input can be any input\.
+ If you have not set up the channel to control startup behavior \(not recommended\), MediaLive starts with the first input in the input attachment list\.

## Failover and failback scenarios<a name="aif-failover-scenarios"></a>

Failover follows this rule:
+ If the active input is unhealthy for 3 seconds, MediaLive switches to the other input\.

You can also manually switch to the other input, if the **Input preference** setting is **EQUAL\_INPUT\_PREFERENCE**\. Switching over manually is useful, for example, if you believe that the active input is unstable\. See [Manually forcing a failover](aif-and-input-switching-failoverpair.md)\.

Failback follows this rule:
+ When the unhealthy input is healthy again for more than 30 seconds, it is marked as healthy\. 

When the input becomes healthy, MediaLive might automatically switch to the healthy input:
+ If the currently active input is the secondary input, MediaLive either stays on the current input \(if the **Input preference** setting is **EQUAL\_INPUT\_PREFERENCE**\) or switches to the primary input \(if the **Input preference** setting is **PRIMARY\_INPUT\_PREFERENCE**\)\.
+ If the active input is the primary input, it always stays on the input\.