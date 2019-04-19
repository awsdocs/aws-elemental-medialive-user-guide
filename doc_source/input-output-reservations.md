# Input and Output Reservations<a name="input-output-reservations"></a>

Reservation offerings are available for inputs and for outputs\. 

## Input Reservation Attributes and Matching<a name="input-reservation-attributes-matching"></a>

An input reservation has these attributes: 
+ Codec 
+ Resolution \(a range\)
+ Bit rate \(a range\)
+ Region that the input runs in

An *input reservation* applies to the cost of processing input\. For a reservation to apply to an input, the attributes of the input reservation must match the fields in the channel's **Input specification**, and the channel must run in the region that is specified in the reservation\. For example, suppose that your input specification for a channel is **AVC**, **HD**, and **Max 20 Mbps**\. A reservation that matches those attributes could apply to the input in that channel\.

## Output Reservation Attributes and Matching<a name="output-reservation-attributes-matching"></a>

An output reservation has these attributes: 
+ Codec 
+ Resolution \(a range\)
+ Bit rate \(a range\)
+ Framerate \(a range\)
+ Region that the input runs in

An *output reservation* applies to the cost of processing output\. For a reservation to apply to an input, the attributes of the output reservation must match the corresponding fields in the channel configuration, and the channel must run in the region that is specified in the reservation\. You can find the fields on the AWS Elemental MediaLive console:
+ For a regular video and audio output, the fields are in the **Video output** section of the channel configuration\. To make most of the fields appear, you must choose a codec on the page\. 
+ For an audio\-only output, the fields are in the **Audio output** section of the channel configuration\. 

There is a match if the value of a field in the channel is equal to or falls within the range of the corresponding attribute\. For example, a bit rate of `29.97 fps` in the channel configuration falls within the range of a bit rate attribute of `<=30fps` in the reservation\.

If just one of the fields does not match its corresponding reservation attribute, then there is no match between the output and reservation\.

## How an Input or Output Reservation Is Applied<a name="how-inputoutput-reservation-applied"></a>

At the start of each monthly billing cycle, AWS replenishes each reservation with the pool of minutes for the month\. 

At the end of the cycle, AWS applies the minutes from a given reservation to reduce the cost for the processed items \(inputs or outputs\) whose attributes match this reservation\. For each minute in the month, AWS determines if one or more matching items was running\. It accumulates these "running minutes" within the hour, up to a maximum of 60 minutes in the hour\. 

After the reservation minutes are used up for the hour, AWS charges the regular rate\-per\-minute for the remainder of the items in that hour\. 

**Running Minutes Can Be Allocated Over Items**  
The running minutes could come from more than one item\. For example, you start Channel A with an input that matches a given reservation\. You have purchased only one instance of this reservation\. After 45 minutes you start Channel B that also has an input that matches a given reservation\. After 15 more minutes you stop Channel A\. The running minutes are accumulated as shown by the green shading in the following illustration\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/reservations-inout-shared2inputs.png)

Here is another example of how different items can consume the running minutes\. Suppose that in one hour you run only outputs that match a given reservation\. You have purchased only one instance of this reservation\. You run these four matching outputs simultaneously for 15 minutes each\. During that hour, you don't run any other matching outputs\. Those four outputs would all contribute to the 60 minutes\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/reservations-inout-shared4outputs.png)

**Processing Bursts Are Not Supported**  
The 60\-minute rule means that reservations can't be used for processing "bursts\."

For example, in one hour you run four outputs that match a given reservation\. You have purchased only one instance of this reservation\. You run these four matching outputs simultaneously for 60 minutes each\. Only one of these outputs is eligible for the reservation because one output is enough to use up the 60 running minutes per hour\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/reservations-inout-bursts.png)

**Unused Minutes**  
If some of the minutes in the reservation are not used, those minutes are lost; the minutes are not transferred to the next month\.

**Running Minutes Can Be Allocated Over Items**  
There are no restrictions regarding channels:
+ For example, the reservation could be consumed based on the processing of one input from one channel and another input from a different channel\. 
+ There is no requirement for all the inputs or outputs in a given channel to be covered by a reservation\.