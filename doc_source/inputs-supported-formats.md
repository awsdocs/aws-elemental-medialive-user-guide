# Supported input formats and protocols<a name="inputs-supported-formats"></a>

The following table lists the supported input types, and describes how the input handles the source content\.

The sections after the table describe how MediaLive ingests a push or pull input\.

[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/inputs-supported-formats.html)

## Ingesting with a pull input<a name="pull-inputs"></a>

A pull input works as follows: the source continually publishes to an endpoint that is outside of MediaLive\. When the channel \(that is connected to the input\) is running, MediaLive connects to the input and ingests the content\. 

When the channel is not running, MediaLive does not connect to the input\. \(There might be other applications that do connect\.\) 

A pull input works with a streaming input \(where the source is continually being published\) or a VOD input \(where the source is made available on the endpoint and then does not change\)\. 

## Ingesting with an RTMP push input<a name="push-inputs"></a>

An RTMP push input works as follows: the source attempts to deliver to an endpoint that is specified in the MediaLive input\. There must be a handshake between the source and the MediaLive channel so that the source has information about the status of the input\. 

When the channel \(that is connected to this input\) is started, MediaLive responds to the handshake message and ingests it\. When the channel is not running, MediaLive does not react; the source goes into a paused state\. 

A push input works only with a streaming source\.

## Ingesting with an RTP push input<a name="push-RTP"></a>

An RTP push input works as follows: the source attempts to deliver to an endpoint that is specified in the MediaLive input\. The source is unaware of whether the content is being ingested by the MediaLive channel\.

When the channel \(that is connected to this input\) is started, MediaLive reacts to the source and ingests it\. When the channel is not running, MediaLive does not react; the source continues to publish to the endpoint, but MediaLive ignores that action\. 

A push input works only with a streaming source\.