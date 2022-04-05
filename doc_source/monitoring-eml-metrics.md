# Monitoring activity using Amazon CloudWatch metrics<a name="monitoring-eml-metrics"></a>

You can monitor AWS Elemental MediaLive using Amazon CloudWatch metrics\. CloudWatch collects raw data that it receives from MediaLive, and processes it into readable, near real\-time metrics that are kept for 15 months\. You use CloudWatch to view the metrics\. Metrics can help you gain a better perspective about how MediaLive is performing over the short term and long term\. 

You can set alarms that watch for certain thresholds, and send notifications or take actions when those thresholds are met\. For more information, see the [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/)\. 

**To view metrics using the CloudWatch console**

Metrics are grouped first by the service namespace, and then by the various dimension combinations within each namespace\. 

1. Open the CloudWatch console at [https://console\.aws\.amazon\.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/)\.

1. In the navigation pane, choose **Metrics**\. Under **All metrics**, choose the **AWS/MediaLive** namespace\.

   The **AWS/MediaLive** namespace was added on June 2, 2021\. To view metrics prior to June 2, 2021 or if the channel has not been restarted since June 2, 2021, the metrics are located in the **MediaLive** custom namespace\.

1. Choose the metric dimension to view the metrics \(for example, choose flow to view metrics per flow\)\.

**To view a list of valid metrics stored for your AWS account using the AWS CLI**
+ At a command prompt, use the following command:

  ```
  aws cloudwatch list-metrics --namespace "AWS/MediaLive"
  ```
+ The **AWS/MediaLive** namespace was added on June 2, 2021\. To view metrics prior to June 2, 2021 or if the channel has not been restarted since June 2, 2021, the metrics are located in the **MediaLive** custom namespace\. Use the following command:

  ```
  aws cloudwatch list-metrics --namespace "MediaLive"
  ```

**Topics**
+ [General information](eml-metrics-gen-info.md)
+ [Global metrics](eml-metrics-global.md)
+ [Input metrics](eml-metrics-input-metrics.md)
+ [Output metrics](eml-metrics-output-metrics.md)
+ [Input device metrics](eml-metrics-input-devices.md)
+ [Pipeline locking metrics](eml-metrics-output-lock.md)