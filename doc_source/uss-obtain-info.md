# Assess source formats and packaging<a name="uss-obtain-info"></a>

Consult the following table for information about how to assess the source formats and packaging\. Read across each row\.


****  

| Information to obtain | Verify the following | 
| --- | --- | 
| Number of sources that the content provider can provide\. | If you plan to implement a [resiliency feature](plan-redundancy.md), make sure that your content provider can deliver the required inputs:[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/uss-obtain-info.html) | 
| Delivery formats and protocols | Find out what format and protocol the upstream system supports for delivery\. Make sure that this format is listed in the table in [Supported input formats and protocols](inputs-supported-formats.md)\. If it is not listed, speak to your content provider about how they can add support for MediaLive\.Note that you don't need to verify this information for content delivered over CDI or content delivered from an AWS Elemental Link\. MediaLive can always handle these input types\. | 
| Whether the upstream system is using the latest SDK | Make sure that the content provider is using the latest version of the [AWS CDI SDK](https://aws.amazon.com/media-services/resources/cdi/) on their upstream CDI source device\. | 
| Whether the source content is a stream or VOD asset | Find out if the source content is a live stream or a VOD asset\.Make sure that MediaLive supports the delivery for the format that you identified\. See the table in [Support for live and file inputs](inputs-live-vs-file.md)\.  | 
| Whether the content is encrypted | MediaLive can ingest encrypted content only from HLS content\.If the source content is HLS and it is encrypted, make sure that it is encrypted in a format that MediaLive supports\. See [Handling encrypted source content in an HLS source](planning-hls-input-encrypted.md)\. If MediaLive doesn't support the available encryption format, find out if you can obtain the content in unencrypted form\. | 
| Only if the source content is RTP, whether it includes FEC\. |  We recommend that the source content include FEC because it is less likely to result in an output that has visual disruptions\.  | 