# Fixed, immediate, and follow switches<a name="ips-switch-types"></a>

You can categorize input switches according to the start types for the switch\. 
+ Fixed – A fixed input switch starts at a specific time\.

  Fixed switches use UTC time\. They don't use the timecode of the input\. 
+ Immediate – An immediate input switch starts as soon as possible\. This type of switch is more like a fixed switch than a follow switch because it interrupts the current input\. The advantage of this switch over a fixed switch is that you don't have to calculate any buffer in the start time\.
+ Follow – A follow input switch starts when the previous input has ended \(when MediaLive has reached the end of the file\)\.

This start type is a property of the switch, not a property of the input itself\. Therefore, in the schedule you can switch to a specific input with a fixed switch, and then later switch to the same input with a follow switch\.

## Types of switches and types of inputs<a name="switch-type-and-file-live-inputs"></a>

The combination of types of switches and types of inputs \(file and live\) means that there are these types of switches:
+ A file input with a fixed start\. The previous input can be a file or live input\. At the specified start time, MediaLive stops ingesting the previous input and switches to the new input\.
+ A file input with an immediate start\. The previous input can be a file or a live input\. As soon as possible after you enter this switch in the schedule, MediaLive stops ingesting the previous input and switches to the new input\. 
+ A file input that follows the previous input\. The previous input must be a file input\. It can't be a live input because a live input doesn't have an end, so the switch would never occur\. 
+ A live input with a fixed start\. The previous input can be a file or live input\. At the specified start time, MediaLive stops ingesting the previous input and switches to the new input\.
+ A live input with an immediate start\. The previous input can be a file or a live input\. As soon as possible after you enter this switch in the schedule, MediaLive stops ingesting the previous input and switches to the new input\. 
+ A live input that follows the previous input\. The previous input must be a file input\. It can't be a live input because a live input doesn't have an end, so the switch would never occur\. 

The following table summarizes the inputs and start types\.


| Current Input | Next Input | Possible Start Type | 
| --- | --- | --- | 
| File | File | Fixed or Immediate | 
| File | File | Follow | 
| File | Live | Fixed or Immediate | 
| File | Live | Follow | 
| Live | File | Fixed or Immediate | 
| Live | Live | Fixed or Immediate | 

## Follow chains<a name="ips-switch-follow-chain"></a>

A series of follow input switches is called a *follow chain*\. When each input ends, MediaLive automatically starts ingesting the next input\. Here is a diagram of a follow chain:

```
   Input A    Fixed or Immediate   File
     Input B  Follow               File
     Input C  Follow               File
     Input D  Follow               File or Live
   Input E    Fixed or Immediate   File or Live
```

The follow chain starts with the *reference action*—the input above the first follow\. It ends with the last follow input\. In the preceding example, the chain starts with the reference action input A and ends with input D\. Inputs A, B, and C must be files because they must have a defined ending so that the next input can successfully follow\. Input E breaks the chain because it is fixed or immediate\.