# Automatic input failover and input switching<a name="aif-and-input-switching"></a>

When you implement automatic input failover, you can still implement input switching\.

**Note**  
The information in this section assumes that you are familiar with the general steps for creating input switches, as described in [Creating actions in the schedule \(console\)](schedule-using-console-create.md)\.

With automatic input failover, your deployment contains an input failover pair that uses up your quota of push inputs for the channel\. You can't attach more push inputs to the channel\. But you can attach more pull inputs, and can therefore set up a multiple\-input channel suitable for input switching using the schedule\. You can perform the following switches:
+ From a pull input to another pull input\.
+ From a pull input to either input in the failover pair\.
+ From the primary input or secondary input to a pull input\.