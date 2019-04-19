# Components of AWS Elemental MediaLive<a name="key-components-of-service"></a>

The key building blocks of AWS Elemental MediaLive are *inputs*, *channels*, and *input security groups*\. A channel in turn consists of output groups, which contain outputs, which contain video, audio, and captions "encodes\."

When a channel is started \(run\), AWS Elemental MediaLive ingests the input\. It then transcodes that video \(and the related audio, captions, and metadata\) and creates output assets\. The information about how to transcode a given input is contained in a channel\.

An [input security group](working-with-input-security-groups.md) is a mechanism to prevent unauthorized third parties from pushing content into a channel that is associated with a "push" input\.