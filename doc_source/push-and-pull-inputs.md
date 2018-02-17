# Ways of Ingesting: Push and Pull<a name="push-and-pull-inputs"></a>

+ A push input works as follows: the source attempts to deliver to an endpoint that is specified in the AWS Elemental MediaLive input\. In the case of RTP protocols, the source is unaware of whether the content is being ingested by the AWS Elemental MediaLive channel\. In the case of RTMP, there must be a handshake between the source and the AWS Elemental MediaLive channel so that the source will have knowledge of the status of the input\. 

  When the channel \(that is connected to this input\) is started, AWS Elemental MediaLive reacts to the source \(RTP\) or responds to the handshake message \(RTMP\) and ingests it\. When the channel is not running, AWS Elemental MediaLive does not react; the source continues to publish to the endpoint \(RTP\) or goes into a paused state \(RTMP\), but AWS Elemental MediaLive does not pay attention\. 

  A push input works only with a streaming source\.

+  A pull input works as follows: the source continually publishes to an endpoint that is outside of AWS Elemental MediaLive\. When the channel \(that is connected to the input\) is running, AWS Elemental MediaLive connects to the input and ingests the content\. 

  When the channel is not running, AWS Elemental MediaLive does not connect to the input\. \(There might be other applications that do connect\.\) 

  A pull input works with a streaming input \(where the source is continually being published\) or a file input \(where the source is put on the endpoint and then does not change until the next time it is put\)\. 