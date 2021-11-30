# Input prepare with clipping<a name="input-prep-clip"></a>

You can prepare for an input switch when the associated input is a file input that includes [input clipping](input-clipping.md)\.

When you set up the prepare input action, you must specify the start and end for the clip\. The values that you enter must exactly match the start and end in the switch action\. If the values are not identical, MediaLive won't prepare the input in advance\.

You might use this file input more than once in the channel, and the start and end might be different in each instance\. Make sure that you change the start and end in each prepare action\.