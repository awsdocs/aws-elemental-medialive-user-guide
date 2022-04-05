# Input metrics<a name="eml-metrics-input-metrics"></a>

Input metrics relate to the video and audio input assets that are presented to MediaLive\.

**Topics**
+ [FEC row packets received](#eml-metrics-fec-row-received)
+ [FEC column packets received](#eml-metrics-fec-col-received)
+ [Input timecodes present](#eml-metrics-input-timecode)
+ [Input video frame rate](#eml-metrics-input-frate)
+ [Network in](#eml-metrics-network-in)
+ [Primary input active](#eml-metrics-primary-active)
+ [RTP packets lost](#eml-metrics-packets-lost)
+ [RTP packets received](#eml-metrics-packets-received)
+ [RTP packets recovered via FEC](#eml-metrics-packets-recovered)
+ [UDP input loss seconds](#eml-metrics-udp-input-loss)
+ [Channel input error seconds](#eml-metrics-input-error-seconds)

## FEC row packets received<a name="eml-metrics-fec-row-received"></a>

The number of forward error correction \(FEC\) row packets received on both FEC streams \(port 5002 and port 5004\)\. A non\-zero value indicates that FEC is functioning\.

This metric is useful only if the channel has an RTP input that includes FEC\.

Follow this guideline:
+ For a channel that implements automatic input failover, we recommend that you choose the dimension set that includes the ActiveInputFailoverLabel dimension, so that you get data for only one input\. 
+ For a channel that doesn't implement automatic input failover, don't include the ActiveInputFailoverLabel dimension set\. The metric won't report any data\.

**Details:**
+ Units: Count\.
+ Meaning of zero: An RTP\-with\-FEC input was being ingested during the period but no FEC row packets were received\.
+ Meaning of no datapoints: There are no inputs with FEC\. Or there are inputs with RTP inputs but none of those inputs are active or being prepared \(by the schedule\)\. Or you included the ActiveInputFailoverLabel in a channel that isn't set up for automatic input failover\. 
+ Supported dimension sets: 

  ChannelId, Pipeline

  ActiveInputFailoverLabel, ChannelId, Pipeline
+ Recommended statistic: Sum\.

## FEC column packets received<a name="eml-metrics-fec-col-received"></a>

The number of FEC column packets received on both FEC streams \(port 5002 and port 5004\)\. A non\-zero value indicates that FEC is functioning\.

This metric is useful only if the channel has an RTP input that includes FEC\.

Follow this guideline:
+ For a channel that implements automatic input failover, we recommend that you choose the dimension set that includes the ActiveInputFailoverLabel dimension, so that you get data for only one input\. 
+ For a channel that doesn't implement automatic input failover, don't include the ActiveInputFailoverLabel dimension set\. The metric won't report any data\.

**Details:**
+ Units: Count\.
+ Meaning of zero: An RTP\-with\-FEC input was being ingested during the period but no FEC column packets were received\.
+ Meaning of no datapoints: There are no inputs with FEC\. Or there are inputs with RTP inputs but none of those inputs are active or being prepared \(by the schedule\)\. Or you included the ActiveInputFailoverLabel in a channel that isn't set up for automatic input failover\. 
+ Supported dimension sets: 

  ChannelId, Pipeline

  ActiveInputFailoverLabel, ChannelId, Pipeline
+ Recommended statistic: Sum\.

## Input timecodes present<a name="eml-metrics-input-timecode"></a>

An indicator of whether a pipeline is receiving input that includes embedded timecodes\. The embedded timecode might be embedded in the source, or it might be embedded in SMPTE\-2038 ancillary data\. 0 \(false\) means it isn’t present\. 1 \(true\) means it is present\.

An embedded timecode that is inaccurate can cause problems in features that use the timecode\. Therefore, it is useful to know whether the timecode that MediaLive is using is an embedded timecode or a system\-clock timecode\. 

The timecode that is associated with the input is used in several features:
+ Input clipping\. This feature can use an embedded timecode or another type of timecode\.
+ Generating a timecode in the outputs\. This feature can use an embedded timecode or another type of timecode\.
+ Pipeline locking\. This feature works only if the input timecode is an embedded timecode; it doesn’t work with a system\-clock timecode\. 

For detailed information about timecodes, see [Timecode configuration](timecode.md)\. 

Follow this guideline:
+ For a channel that implements automatic input failover, we recommend that you choose the dimension set that includes the ActiveInputFailoverLabel dimension, so that you get data for only one input\. 
+ For a channel that doesn't implement automatic input failover, don't include the ActiveInputFailoverLabel dimension set\. The metric won't report any data\.

**Details:**
+ Units: None\.
+ Meaning of zero: False \(there is no embedded timecode\)\.
+ Meaning of no datapoints: The channel is not running, or the channel is running but MediaLive isn’t receiving content \(for example, the input is a push input and the upstream system hasn’t started pushing content\)\. Or you included the ActiveInputFailoverLabel in a channel that isn't set up for automatic input failover\. 
+ Supported dimension sets:

  ChannelId, Pipeline

  ActiveInputFailoverLabel, ChannelId, Pipeline
+ Recommended Statistic: Minimum or maximum\. The other statistics have no meaning\.

## Input video frame rate<a name="eml-metrics-input-frate"></a>

The frame rate of the source video\. 

This metric is an indicator of the health of the input\. If the value isn't stable, investigate determine if there are problems with your source,and/or problems in the network between MediaLive and the upstream system\.

Follow this guideline:
+ For a channel that implements automatic input failover, we recommend that you choose the dimension set that includes the ActiveInputFailoverLabel dimension, so that you get data for only one input\. 
+ For a channel that doesn't implement automatic input failover, don't include the ActiveInputFailoverLabel dimension set\. The metric won't report any data\.

**Details:**
+ Units: Frames per second\.
+ Meaning of zero: The input has been received at some point since the channel started, but no frames were received in the current period\. 
+ Meaning of no datapoints: No input has been received since this channel started\. Or you included the ActiveInputFailoverLabel in a channel that isn't set up for automatic input failover\. 
+ Supported dimension sets: 

  ChannelID, Pipeline 

  ActiveInputFailoverLabel, ChannelId, Pipeline
+ Recommended statistic: Max\.

## Network in<a name="eml-metrics-network-in"></a>

The rate of traffic coming into MediaLive\. This number includes all traffic received into MediaLive—push inputs, pull inputs, responses from the upstream system of a pull input, responses from the downstream system for any output, and instance traffic such as DNS resolution and NTP\. Even when a channel is not ingesting, there will be some traffic\.

It’s useful to set up to capture the average traffic rate over a long period\. Then when you have established the normal rate, change the period to a short time, so that you can easily spot deviations from the normal rate, or collect information about how bursty a channel is\.

Here are some guidelines on interpreting this metric:
+ If the rate seems to be normal, then you might infer that the channel is running and successfully ingesting inputs\. 
+ If the number is lower than normal, then your channel might be running but without inputs attached\. Keep in mind that there are charges for running channels even when they aren’t ingesting input\.

**Details:**
+ Units: Megabits per second\. 
+ Meaning of zero: No traffic is being received\.
+ Meaning of no datapoints: The channel is not running\.
+ Supported dimension sets: ChannelId, Pipeline
+ Recommended statistic: All the statistics are useful for this metric\.

## Primary input active<a name="eml-metrics-primary-active"></a>

An indicator of whether the primary input in an automatic input failover pair is active\. A value of 1 means that the primary input is active and is therefore healthy\. A value of 0 means that it is inactive\.

For information about input failover pairs in the automatic input failover feature, see [Implementing automatic input failover](automatic-input-failover.md)\.

This metric is useful if you have set up the automatic input failover feature with the input preference set to Primary Input Preference\. The metric doesn’t provide any meaningful data if the input preference is set to Equal Input Preference\. 

**Details:**
+ Units: None\.
+ Meaning of zero: False \(the primary input is inactive\)\.
+ Meaning of no datapoints: The channel is not set up for automatic input failure\.
+ Supported dimension sets: ChannelId, Pipeline
+ Recommended statistic: Minimum \(primary input is inactive\) or maximum \(primary input is active\)\.

## RTP packets lost<a name="eml-metrics-packets-lost"></a>

The number of RTP packets that are lost in the incoming transmission\. *Lost *means packets that couldn't be recovered by FEC\. 

This metric only applies to RTP input types\.

Received packets \+ Recovered packets \+ Lost packets = Total expected for the period, if the period and dimensions for the three metrics are set identically for the three metrics\.

These three RTP packet metrics are useful for monitoring the health of the input transmission\. If this metric is non\-zero, the first troubleshooting step is to look at the two [FEC metrics](#eml-metrics-fec-row-received), to determine whether FEC is functioning\. If FEC is functioning well, the next step is to investigate problems in the upstream network\.

Follow this guideline:
+ For a channel that implements automatic input failover, we recommend that you choose the dimension set that includes the ActiveInputFailoverLabel dimension, so that you get data for only one input\. 
+ For a channel that doesn't implement automatic input failover, don't include the ActiveInputFailoverLabel dimension set\. The metric won't report any data\.

**Details:**
+ Units: Count\.
+ Meaning of zero: An RTP\-with\-FEC input was being ingested during the period, but no packets were lost\.
+ Meaning of no datapoints: No inputs are ingesting RTP\. Or there are RTP inputs but none of those inputs are active or being prepared \(by the schedule\)\. Or you included the ActiveInputFailoverLabel in a channel that isn't set up for automatic input failover\. 
+ Supported dimension sets: 

  ChannelId, Pipeline

  ActiveInputFailoverLabel, ChannelId, Pipeline
+ Recommended statistic: Sum\.

## RTP packets received<a name="eml-metrics-packets-received"></a>

The number of RTP packets received in an RTP input\. This number includes the main RTP source \(port 5000\) and the FEC data \(ports 5002 and 5004\)\. 

This metric only applies to RTP input types\.

Received packets \+ Recovered packets \+ Lost packets = Total expected for the period, if the periods for the three metrics are set identically\.

These three RTP packet metrics are useful for monitoring the health of the input transmission\.

Follow this guideline:
+ For a channel that implements automatic input failover, we recommend that you choose the dimension set that includes the ActiveInputFailoverLabel dimension, so that you get data for only one input\. 
+ For a channel that doesn't implement automatic input failover, don't include the ActiveInputFailoverLabel dimension set\. The metric won't report any data\.

**Details:**
+ Unit: Count\.
+ Meaning of zero: An RTP\-with\-FEC input was being ingested during the period, but no packets were received\.
+ Meaning of no datapoints: No inputs are ingesting RTP\. Or there are inputs with RTP inputs but none of those inputs are active or being prepared \(by the schedule\)\. Or you included the ActiveInputFailoverLabel in a channel that isn't set up for automatic input failover\. 
+ Supported dimension sets: 

  ChannelId, Pipeline

  ActiveInputFailoverLabel, ChannelId, Pipeline
+ Recommended statistic: Sum\.

## RTP packets recovered via FEC<a name="eml-metrics-packets-recovered"></a>

The number of RTP packets recovered via FEC\.

This metric only applies to RTP input types\.

Received packets \+ Recovered packets \+ Lost packets = Total expected for the period, if the periods for the three metrics are set identically\.

These three RTP packet metrics are useful for monitoring the health of the input transmission\.

Follow this guideline:
+ For a channel that implements automatic input failover, we recommend that you choose the dimension set that includes the ActiveInputFailoverLabel dimension, so that you get data for only one input\. 
+ For a channel that doesn't implement automatic input failover, don't include the ActiveInputFailoverLabel dimension set\. The metric won't report any data\.

**Details:**
+ Units: Count\.
+ Meaning of zero: An RTP\-with\-FEC input was being ingested during the period, but no packets were recovered\.
+ Meaning of no datapoints: No inputs are ingesting RTP\. Or there are inputs with RTP inputs but none of those inputs are active or being prepared \(by the schedule\)\. Or you included the ActiveInputFailoverLabel in a channel that isn't set up for automatic input failover\. 
+ Supported dimension sets: 

  ChannelId, Pipeline

  ActiveInputFailoverLabel, ChannelId, Pipeline
+ Recommended statistic: Sum\.

## UDP input loss seconds<a name="eml-metrics-udp-input-loss"></a>

The number of seconds \(the *input loss period*\) for which the channel has not received packets from the source of an RTP or MediaConnect input\. Each datapoint has a value between 0 and 10 seconds\. 

This metric is useful for monitoring the health of the input transmission\.

You should look at the datapoints over several 10\-second windows\. 
+ Consistent values of 0 \(all packets received\) – This pattern tells you that the input is healthy\.
+ Consistent values of 10 \(no packets received\) – This pattern tells you that the input is not healthy\.
+ A range of values starting at 0 and ending at 0 – This pattern tells you the input was not healthy but that it has recovered\. For example, 0,2,10,10,5,10,6,2,0,0,0\.
+ A range of values that don’t return to 0 – This pattern tells you that the input is not healthy\. For example, 0,10,9,2,8,3,10,10,8,2\.

Also follow this guideline:
+ For a channel that implements automatic input failover, we recommend that you choose the dimension set that includes the ActiveInputFailoverLabel dimension, so that you get data for only one input\. 
+ For a channel that doesn't implement automatic input failover, don't include the ActiveInputFailoverLabel dimension set\. The metric won't report any data\.

**Details:**
+ Units: Seconds\.
+ Meaning of zero: There was no input loss\.
+ Meaning of no datapoints: No inputs are ingesting RTP\. Or there are inputs with RTP inputs but none of those inputs are active or being prepared \(by the schedule\)\. Or you included the ActiveInputFailoverLabel in a channel that isn't set up for automatic input failover\. 
+ Supported dimension sets: 

  ChannelId, Pipeline

  ActiveInputFailoverLabel, ChannelId, Pipeline
+ Recommended statistic: Sum\.

## Channel input error seconds<a name="eml-metrics-input-error-seconds"></a>

The number of seconds in which the channel input contained one or more unrecoverable packets\.

This metric only applies to Channel inputs of type RTP Push or MediaConnect\.

This metric is useful for monitoring the health of the input\. It provides a time\-based measurement for packet loss\.

Follow this guideline:
+ For a channel that implements automatic input failover, we recommend that you choose the dimension set that includes the ActiveInputFailoverLabel dimension, so that you get data for only one input\. 
+ For a channel that doesn't implement automatic input failover, don't include the ActiveInputFailoverLabel dimension set\. The metric won't report any data\. 

**Details:**
+ Units: Count\.
+ Meaning of zero: An RTP Push or MediaConnect input was being ingested and no packets were lost\.
+ Meaning of no datapoints: There are no RTP Push or MediaConnect inputs active or being prepared \(by the schedule\)\. Or you included the ActiveInputFailoverLabel in a channel that isn't set up for automatic input failover\. 
+ Supported dimension sets: 

  ChannelId, Pipeline

  ActiveInputFailoverLabel, ChannelId, Pipeline
+ Recommended statistic: Sum\.