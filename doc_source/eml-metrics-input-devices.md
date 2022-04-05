# Input device metrics<a name="eml-metrics-input-devices"></a>

Input device metrics relate to physical input devices, such as the AWS Elemental Link device family, that send video and audio assets into the MediaLive service\.

For more information about the Link device family, see [AWS Elemental Link](http://aws.amazon.com/medialive/features/link/)\.

**Dimensions for input devices**
+ InputDeviceId – This value is a unique identifier for each input device\.
+ Device Type – The specific model type of the input device, such as AWS Elemental Link HD or UHD\.

**Topics**
+ [Using SDI](#eml-metrics-using-SDI)
+ [Using HDMI](#eml-metrics-using-HDMI)
+ [Input locked](#eml-metrics-input-locked)
+ [Encoder running](#eml-metrics-encoder-running)
+ [Linked to stream endpoint](#eml-metrics-linked-to-stream-endpoint)
+ [Streaming](#eml-metrics-streaming)
+ [Temperature](#eml-metrics-device-temperature)
+ [Configured bitrate](#eml-metrics-device-configured-bitrate)
+ [Encoder bitrate](#eml-metrics-device-encoder-bitrate)
+ [Configured bitrate available](#eml-metrics-device-available-bitrate)
+ [Total packets](#eml-metrics-total-packets)
+ [Recovered packets](#eml-metrics-recovered-packets)
+ [Not recovered packets](#eml-metrics-not-recovered-packets)
+ [Error seconds](#eml-metrics-error-seconds)
+ [Use cases](#eml-metrics-device-use-cases)

## Using SDI<a name="eml-metrics-using-SDI"></a>

Indicates if SDI is the currently selected input for the device\.

A value of 0 indicates SDI is not the active input\. A value of 1 indicates SDI is the active input\.

**Details:**
+ Units: Boolean\.
+ Meaning of zero: SDI is not the selected input\.
+ Meaning of no datapoints: The device is not connected to AWS\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Minimum \(SDI input is inactive\) or maximum \(SDI input is active\)\.

## Using HDMI<a name="eml-metrics-using-HDMI"></a>

Indicates if HDMI is the currently selected input for the device\.

A value of 0 indicates HDMI is not the active input\. A value of 1 indicates HDMI is the active input\.

**Details:**
+ Units: Boolean\.
+ Meaning of zero: HDMI is not the selected input\.
+ Meaning of no datapoints: The device is not connected to AWS\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Minimum \(HDMI input is inactive\) or maximum \(HDMI input is active\)\.

## Input locked<a name="eml-metrics-input-locked"></a>

Indicates if the device has successfully locked on to the input signal\.

A value of 0 indicates the input signal is not locked\. A value of 1 indicates the input is successfully locked\.

**Details:**
+ Units: Boolean\.
+ Meaning of zero: The device is not locked onto a signal\. Either because nothing is plugged in, or the device is unable to detect the input signal\.
+ Meaning of no datapoints: The device is not connected to AWS\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Maximum \(indicates the signal is successfully locked\)\.

## Encoder running<a name="eml-metrics-encoder-running"></a>

The encoder is successfully processing the input signal\.

A value of 0 indicates the encoder is not running and the input is not being processed\. A value of 1 indicates the encoder is successfully processing the locked input signal\.

**Details:**
+ Units: Boolean\.
+ Meaning of zero: The encoder is not processing the input signal\. Verify that a valid signal is being passed to the input\.
+ Meaning of no datapoints: The device is not connected to AWS\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Maximum \(indicates the encoder is successfully processing\)\.

## Linked to stream endpoint<a name="eml-metrics-linked-to-stream-endpoint"></a>

The device is connected to the streaming endpoint in AWS\.

A value of 0 indicates the device is not connected to the streaming endpoint\. A value of 1 indicates the device is successfully connected to the streaming endpoint\.

**Details:**
+ Units: Boolean\.
+ Meaning of zero: The device is not connected to a streaming endpoint\.
+ Meaning of no datapoints: The device is not connected to AWS\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Maximum \(indicates the device is successfully connected to the streaming endpoint\)\.

## Streaming<a name="eml-metrics-streaming"></a>

The device is successfully streaming the input signal to MediaLive\.

A value of 0 indicates the input signal is not being streamed through to MediaLive\. A value of 1 indicates the device is successfully streaming the input signal to MediaLive\.

**Details:**
+ Units: Boolean\.
+ Meaning of zero: The device is not fully streaming\. Verify the previous metrics are displaying the recommended statistics\. 
+ Meaning of no datapoints: The device is not connected to AWS\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Maximum \(indicates the device is successfully streaming the input signal to MediaLive\)\.

## Temperature<a name="eml-metrics-device-temperature"></a>

The device temperature in degrees Celsius\. Consult your device's documentation for recommended operating conditions\.

**Details:**
+ Units: Degrees Celsius\.
+ Meaning of zero: a temperature of zero degrees Celsius is below the recommended operating temperature of the AWS Elemental Link device family\.
+ Meaning of no datapoints: The device is not connected to AWS\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Within the temperature range listed for your devices operating conditions\.

## Configured bitrate<a name="eml-metrics-device-configured-bitrate"></a>

The configured **Maximum bitrate**\.

This value represents the highest bitrate that the input signal will be encoded at\.

**Details:**
+ Units: Bits per second\.
+ Meaning of zero: Not applicable\. Consult the minimum required bitrates for your device\.
+ Meaning of no datapoints: The device is not connected to AWS\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: P90\.

## Encoder bitrate<a name="eml-metrics-device-encoder-bitrate"></a>

The actively encoded bitrate\.

This value represents the actual bitrate that is being encoded\. If a **Maximum bitrate** has been configured \(this is represented by the **Configured bitrate** value\) this value will not exceed it\.

**Details:**
+ Units: Bits per second\.
+ Meaning of zero: The encoder is not running\.
+ Meaning of no datapoints: The device is not connected to AWS\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: P90\.

## Configured bitrate available<a name="eml-metrics-device-available-bitrate"></a>

The portion of **Configured bitrate** the device is able to satisfy based on network conditions\.

The bitrate that is actively encoded is a result of the configured bitrate and the network conditions at the time the metric is measured\. If a **Maximum bitrate ** is configured, the input device will evaluate the network connection and deliver at a bitrate below the maximum, as long as the network supports it\. If no **Maximum bitrate** value is set, the input device will determine the best bitrate for the network connection between the device and the MediaLive service\. The **Encoder bitrate** metric represents the actual encoding bitrate, whether or not a **Maximum bitrate** value is set\.

**Details:**
+ Units: Percentage\.
+ Meaning of zero: Not applicable\. While the encoder is running, a non\-zero bitrate will be encoded\.
+ Meaning of no datapoints: The device is not streaming\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: P90\.

## Total packets<a name="eml-metrics-total-packets"></a>



The total number of packets that were successfully delivered to the AWS streaming endpoint\.

**Details:**
+ Units: Count\.
+ Meaning of zero: No packets are being delivered from the Link device to the streaming endpoint\.
+ Meaning of no datapoints: The device is not streaming\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Sum\.

## Recovered packets<a name="eml-metrics-recovered-packets"></a>



The number of packets that were lost during transit, but recovered by error correction\.

**Details:**
+ Units: Count\.
+ Meaning of zero: The stream is healthy\. Successfully delivered packets did not require error correction\.
+ Meaning of no datapoints: The device is not streaming\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Sum\.

## Not recovered packets<a name="eml-metrics-not-recovered-packets"></a>



The number of packets that were lost during transit and were not recovered by error correction\.

**Details:**
+ Units: Count\.
+ Meaning of zero: The stream is healthy\. No packets have been lost in transit from the Link device to the streaming endpoint\.
+ Meaning of no datapoints: The device is not streaming\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Sum\.

## Error seconds<a name="eml-metrics-error-seconds"></a>



The number of seconds in which one or more packets were dropped and not recovered\.

**Details:**
+ Units: Count\.
+ Meaning of zero: The stream is healthy\. No packets have been lost in transit from the Link device to the streaming endpoint\.
+ Meaning of no datapoints: The device is not streaming\.
+ Supported dimension sets: InputDeviceId, DeviceType
+ Recommended statistic: Sum\.

## Use cases<a name="eml-metrics-device-use-cases"></a>

**Scenario: My device is not streaming\.**

If you have started a channel but find that the stream is not functioning correctly, you can use metrics to isolate the source of the issue\. The following metrics represent different points from the input source to the final stream\. An issue at any point could indicate the reason why your stream is not working\. In order, from input source to final stream, the metrics to look at are the following:
+ **Using SDI**/**Using HDMI**
  + Verify the Link device is configured to use the input type that matches the connected source\.
+ **Input locked**
  + If this is 0, the encoder is not able to identify a signal from the connected source\. Verify that you have a connected source that matches the selected input type\.
+ **Encoder running**
  + If this is 0, the Link device is not able to encode the signal\. If the input is locked, this could indicate a problem with the Link device\.
+ **Linked to stream endpoint**
  + If this is 0, the Link device is not able to connect to its streaming endpoint in the AWS service\. Verify the encoder is running by checking the **Encoder running** metric\. If the encoder is running, verify that port 2088 is not blocked on your network\. For a list of ports that must be open, consult the [HD](https://docs.aws.amazon.com/elemental-onprem/latest/pdf/AWS_Elemental_Data_Sheet_Link.pdf) datasheet or [UHD](https://docs.aws.amazon.com/elemental-onprem/latest/pdf/AWS_Elemental_Link_UHD_Specification_Sheet.pdf) datasheet\.
+ **Streaming**
  + If this is 0, verify that the channel has been started\. If the value is still 0, investigate the previous metrics to isolate the source of the problem\.

**Scenario: My video quality is poor\.**

Poor video quality can be the result of poor network performance\. To determine if network performance is the cause, look at **Configured bitrate**, **Encoder bitrate**, and **Configured bitrate available**\. If **Configured bitrate available** is consistently less than 100%, that indicates that the Link device's network connection is unable to satisfy the configured bandwidth\. As a result, the **Encoder bitrate** is reduced to adjust to the poor network connection\.

When the **Encoder bitrate** is reduced due to a poor network connection, the encoder attempts to maintain video quality by preventing packet loss\. However, the resolution, frame rate, and scene complexity can affect the encoder’s ability to produce a high quality stream\. We recommend that HD devices running at 60 frames per second \(FPS\) maintain an **Encoder bitrate** of at least five Megabits per second \(Mbps\)\. UHD devices running at 60 FPS should maintain an **Encoder bitrate** of 10 to 15 Mbps\.

You can use the following metrics to troubleshoot the frequency and severity of network interruptions:
+ **Recovered packets**
  + If this is greater than 0, packets were dropped in transit and were recovered by error correction\. Although recovered packets will not impact video quality, consistent packet drops can indicate that the stream might experience issues in the future\.
+ **Not recovered packets**
  + If this is greater than 0, packets were dropped in transit and were not recovered by error correction\. A loss of packets can result in poor video quality\. You can compare this with the value of **Total packets** to determine what percentage of incoming packets were lost\.
+ **Error seconds**
  + If this is greater than 0, it indicates the stream experienced one or more seconds in which packets were dropped and not recovered\. This metric quantifies video quality issues as a total period of impacted time, rather than a packet count\.