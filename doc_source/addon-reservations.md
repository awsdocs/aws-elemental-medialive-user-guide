# Add\-on Reservations<a name="addon-reservations"></a>

Reservations are available for those items in [the MediaLive price list](https://aws.amazon.com/medialive/pricing/), such as codec licenses, that are considered to be add\-ons\. 

An add\-on reservation applies to the cost of the add\-on for the entire channel\. The reservation reduces the cost of the add\-on regardless of how many times the add\-on applies to the channel\. For example, if three outputs in the same channel both use an advanced audio codec, you need only one reservation to reduce the cost of the add\-on\. You don't need three reservations for this channel\.

## Reservation Attributes<a name="addon-reservation-attributes"></a>

The add\-on reservations have these attributes:
+ Add\-on \(Advanced Audio, or Audio Normalization\)
+ Region in which the channel is running

## How an Add\-on Reservation Is Applied<a name="how-addon-reservation-applied"></a>

At the start of each monthly billing cycle, AWS replenishes each add\-on reservation with the pool of minutes for the month\. 

At the end of the cycle, AWS applies the minutes from a given reservation to reduce the cost for channels that use the add\-on\. For each minute in the month, it determines if one or more matching channels was running\. A channel matches the reservation if the add\-on feature is enabled\. 

AWS accumulates these running minutes within the hour, up to a maximum of 60 minutes in the hour\. After the reservation minutes are used up for the hour, AWS charges the regular rate\-per\-minute for the remainder for those channels for that hour\. 

**Add\-ons Are Per Channel**  
A channel matches the reservation if the add\-on feature is enabled one or more times\. Within one channel, the number of outputs that use the add\-on isn't relevant; the reservation is consumed only once for the entire channel\. For example, if there are two outputs in one channel that enable audio normalization, only one reservation is consumed\. 

**Running Minutes Can Be Allocated Over Channels**  
The same rule applies to add\-ons as to [input and output reservations](input-output-reservations.md#how-inputoutput-reservation-applied), except that the item is always a channel\. For example, you start Channel A with two outputs that match the Advanced Audio reservation\. You have purchased only one instance of this reservation\. After 45 minutes you start Channel B that has one output that matches the same reservation\. After 15 more minutes you stop Channel A\. The running minutes are accumulated as shown by the green shading in the following illustration\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/reservations-addon-shared2channels.png)

Here is another example of how different channels can consume the running minutes\. Suppose that in one hour you run only channels that match the Advanced Audio reservation\. You have purchased only one instance of this reservation\. You run these four matching outputs simultaneously for 15 minutes each\. During that hour, you don't run any other matching outputs\. Those four outputs would all contribute to the 60 minutes\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/reservations-addon-shared4channels.png)

**Licensing Bursts Are Not Supported**  
The same rule applies to add\-ons as to [input and output reservations](input-output-reservations.md#how-inputoutput-reservation-applied), except that the item is always a channel\. For example, in one hour you run four channels that match the Advanced Audio reservation\. You have purchased only one instance of this reservation\. You run these four matching channels simultaneously for 60 minutes each\. Only one of these channels is eligible for the reservation because one channel is enough to use up the 60 running minutes per hour\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/reservations-addon-bursts.png)

**Unused Minutes**  
At the end of the cycle, if some of the minutes in the reservation are not used, those minutes are lost; the minutes are not transferred to the next month\.