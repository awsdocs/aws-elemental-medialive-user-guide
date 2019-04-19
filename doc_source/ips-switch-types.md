# Types of Switches—Fixed, Follow, and Follow Chains<a name="ips-switch-types"></a>

There are two types of input switch start modes:
+ Fixed: These input switches start at a specific UTC time\.
+ Follows: These input switches start when the previous input has ended \(when MediaLive has reached the end of the file\)\.

Note that switches at a fixed time use UTC time\. They do not use the timecode of the input\. 

The combination of types of switches and types of inputs \(file and live\) means that there are these types of switches:
+ A file input with a fixed start\. The previous input can be a file or live input\. At the specified start time, MediaLive stops ingesting the previous input and switches to the new input\.
+ A file input that follows the previous input\. The previous input must be a file input\. It can't be a live input because a live input doesn't have an end, so the switch would never occur\. 
+ A live input with a fixed start\. The previous input can be a file or live input\. At the specified start time, MediaLive stops ingesting the previous input and switches to the new input\.
+ A live input that follows the previous input\. The previous input must be a file input\. It can't be a live input because a live input doesn't have an end, so the switch would never occur\. 

The following table summarizes the inputs and start types\.


| Current Input | Next Input | Possible Start Type | 
| --- | --- | --- | 
| File | File | Fixed | 
| File | File | Follow | 
| File | Live | Fixed | 
| File | Live | Follow | 
| Live | File | Fixed | 
| Live | Live | Fixed | 

A series of follow input switches is called a *follow chain*\. When each input ends, MediaLive automatically starts ingesting the next input\. Here is a diagram of a follow chain:

```
   Input A    Fixed   File
     Input B  Follow  File
     Input C  Follow  File
     Input D  Follow  File or Live
   Input E    Fixed   File or Live
```

The follow chain starts with the input above the first follow and ends with the last follow input\. In the preceding example, the chain starts with input A and ends with input D\.

The last input can be file or live\. Either of these types can come before a fixed input \(input E\)\.

The other inputs \(inputs A, B, C\) in the follow chain must be files because they must have a defined ending so that the next input can successfully follow\.