# How input prepare actions behave at runtime<a name="input-prep-runtime"></a>

All prepare actions that you add to the schedule sit in the schedule until the start time\. At the start time \(which can be fixed, immediate, or following an input switch\), MediaLive stops any input prepare that is currently active, and starts the new input prepare\.

Eventually, MediaLive switches to the associated input\. At this point, MediaLive doesn't stop preparing the input\. The input prepare continues either indefinitely or until another input prepare starts\. This perpetual prepare characteristic can be useful\. For an example, see [scenario B](plan-prep-tips.md#plan-prep-tips-scenario-B)\.

If a channel fails, MediaLive automatically restarts the channel\. If the schedule indicates that there is an upcoming immediate switch action, and the schedule also contains a prepare action for that input, then MediaLive starts preparing the input again\. You don't need to take any steps\. 