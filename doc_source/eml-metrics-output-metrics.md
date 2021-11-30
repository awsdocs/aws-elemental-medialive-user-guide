# Output metrics<a name="eml-metrics-output-metrics"></a>

**Topics**
+ [Active outputs](#eml-metrics-active-outputs)
+ [Fill msec](#eml-metrics-fill)
+ [Output audio level dBFS](#eml-metrics-audio-dbfs)
+ [Output audio level LKFS](#eml-metrics-audio-lkfs)
+ [Network Out](#eml-metrics-network-out)
+ [Output 4xx errors](#eml-metrics-4xx)
+ [Output 5xx errors](#eml-metrics-5xx)

## Active outputs<a name="eml-metrics-active-outputs"></a>

The number of outputs that are being produced and successfully written to the destination\.

**Details:**
+ Units: Count\.
+ Meaning of zero: None of the outputs are successfully being written to their destinations\.

  If the outputs are configured to pause on input loss \(according to the **Input loss action **setting for the output group\), that behavior might be intentional\.
+ Meaning of no datapoints: The channel isn’t generating output audio \(it might still be starting or waiting for initial input\)\.
+ Supported dimension sets: OutputGroupName, ChannelId, Pipeline
+ Recommended statistic: Minimum, which helps you identify situations when one or more outputs is not being produced\.

## Fill msec<a name="eml-metrics-fill"></a>

The current length of time \(the *fill period*\) during which MediaLive has filled the video output with fill frames\. The fill period starts when the pipeline does not receive content from the input within the* expected time\.* The *expected time *is based on the input frame rate\. The fine points of the fill frame behavior are controlled by the input loss behavior fields in the channel configuration\. For information about these fields, see [Global configuration \- Input loss behavior](creating-a-channel-step3.md#input-loss-behavior)\.

A value of 0 means that fill frames aren't being used\. A non\-zero value means that fill frames are being used and that the input is unhealthy\.

The count is capped at 60,000 milliseconds \(1 minute\), which means that after the cap, the metric will be 60,000 until it drops to zero\. 

Use this metric as follows:
+ If you have automatic input failover enabled – This metric typically shows zero all the time, even when there is a failover\.  The channel fails over to the other input immediately, which means that there is no need for MediaLive to use fill frames\.
+ If you don’t have automatic input failover enabled – A non\-zero value indicates that the input has failed, has been disrupted, or isn't keeping up with real time\.

**Details:**
+ Units: Count\.
+ Meaning of zero: The input is healthy and the output contains the expected video \(rather than fill frames\)\.
+ Meaning of no datapoints: The channel isn’t producing output, which means that it isn’t running\. Or that it is running but it is initializing, or waiting for initial input, or paused\.
+ Supported dimension sets: ChannelId, Pipeline
+ Recommended statistic: Maximum, to capture the capped count when fill frames are being used\.

## Output audio level dBFS<a name="eml-metrics-audio-dbfs"></a>

The output audio level in decibels relative to full scale \(dBFS\)\.

**Details:**
+ Units: Count\.
+ Meaning of zero: The output audio level is 0 dBFS\.
+ Meaning of no datapoints: The channel isn’t generating output audio \(it might still be starting or waiting for initial input\)\.
+ Supported dimension sets: AudioDescriptionName, ChannelId, Pipeline
+ Recommended statistic: Minimum or maximum, which identify the lowest and highest audio level during the period\.

## Output audio level LKFS<a name="eml-metrics-audio-lkfs"></a>

The output audio level in loudness, K\-weighted, relative to full scale \(LKFS\)\.

**Details:**
+ Units: Count\.
+ Meaning of zero: Output audio level is 0 LFKS\.
+ Meaning of no datapoints: The channel isn’t generating output audio \(it might still be starting or waiting for initial input\)\.
+ Supported dimension sets: AudioDescriptionName, ChannelId, Pipeline
+ Recommended statistic: Minimum or maximum, which identify the lowest and highest audio level during the period\.

## Network Out<a name="eml-metrics-network-out"></a>

The rate of traffic out of MediaLive\. This number includes all traffic sent from MediaLive — the media output, HTTP GET requests for pull inputs, NTP traffic, and DNS traffic\. Even when a channel is not delivering output, there will be some traffic\. 

**Details:**
+ Units: Megabits per second\.
+ Meaning of zero: No traffic is being sent\.
+ Meaning of no datapoints: The channel is not running\.
+ Supported dimension sets: ChannelId, Pipeline
+ Recommended statistic: Average\.

## Output 4xx errors<a name="eml-metrics-4xx"></a>

The number of 4xx HTTP errors that have been received from the destination while delivering output\.

**Details:**
+ Units: Count\.
+ Meaning of zero: The output is being delivered over HTTP and there are no errors\.
+ Meaning of no datapoints: The output is not being delivered to the destination over HTTP\. Or the channel is not running\.
+ Supported dimension sets: OutputGroupName, ChannelId, Pipeline
+ Recommended statistic: Sum\.

## Output 5xx errors<a name="eml-metrics-5xx"></a>

The number of 5xx HTTP errors that have been received from the destination while delivering output\.

**Details:**
+ Units: Count\.
+ Meaning of zero: The output is being delivered over HTTP and there are no errors\.
+ Meaning of no datapoints: The output is not being delivered to the destination over HTTP\. Or the channel is not running\.
+ Supported dimension sets: OutputGroupName, ChannelId, Pipeline
+ Recommended statistic: Sum\.