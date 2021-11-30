# Input prepare and automatic input failover<a name="input-prep-aif"></a>

Your channel might include some inputs that are set up as [automatic input failover pairs](automatic-input-failover.md)\. 

When you set up the prepare input action for an input that is a failover pair, make sure that you specify the primary input as the associated input \(in the **Input attachment** field on the **Create schedule action** page\)\. If you specify the secondary input, MediaLive won't prepare the inputs in advance\.

When MediaLive performs the prepare action, it prepares both inputs\. This means that a later input switch action can be to either of the inputs in the failover pair\.

Here is a scenario that illustrates some of the key behavior:

1. You prepare input A by specifying the primary input\. The prepare starts\.

1. You switch to input A by specifying the primary input\. The channel switches to input A\.

1. You then prepare input B\. The prepare starts\.

1. You notice that input A is degrading, so you switch to the secondary input\. You don't have to prepare input A\. Even though you have started to prepare input B, the secondary input for input A is still being prepared, as part of the automatic input failover process\. Therefore, the switch proceeds seamlessly\.

1. You switch away from input A\.

1. You prepare input A again, because you are going to switch to it later\. You specify the primary input\. The prepare starts\.

1. You switch to input A\. But you then switch to the secondary input, because the primary input is still degraded\. You can switch to the secondary input because, even though you specified the primary input in the prepare action, MediaLive always prepares both inputs\.