# Channel Class<a name="channel-class"></a>

When you [planned the workflow](plan-redundancy-mode.md), you decided whether to set up the channel as a standard channel \(with two pipelines\) or a single\-pipeline channel\. You must now specify the class in the channel configuration\. 

For **Channel class**, choose `STANDARD` or `SINGLE_PIPELINE`\.

## Standard Class<a name="channel-class-standard"></a>

With this class, the channel contains two pipelines\. The input for the channel has two entry points\. The upstream system sends identical source streams to these two entry points, to provide content to two pipelines within the channel\. MediaLive performs identical processing on both pipelines\. For each output that you configure \(for example, for both HLS output and RTMP output\), the two pipelines deliver identical content to two destinations on the downstream system\. 

We strongly recommend that you set up all channels in as standard channels\.

## Single Pipeline Class<a name="channel-class-single-pipeline"></a>

With this class, the channel contains one pipeline\. For each output that you configure, the channel delivers content to one destination on the downstream system\.