# Setting up the Upstream System<a name="planning-upstream"></a>

The upstream system is the system that is streaming the video to AWS Elemental MediaLive\. A contribution encode "on the ground" is a typical upstream system\. You must perform some setup of your upstream system before you start working in AWS Elemental MediaLive\. 

Here are some guidelines for setting up the upstream video source that is the input into AWS Elemental MediaLive\.

+ Make sure the upstream system is capable of streaming using one of the supported protocols for input\. See [[ERROR] BAD/MISSING LINK TEXT](inputs-supported-containers.md)\. If your chosen protocol is RTP push, make sure to send over RTP, not UDP\. The UDP protocol is not supported as an input into AWS Elemental MediaLive\.

+ Determine if your chosen protocol uses a "push" or a "pull"; see [[ERROR] BAD/MISSING LINK TEXT](inputs-supported-containers.md)\.

+ Find out how the input is encoded \- the video codecs, audio codecs, and captions formats it uses\. Make sure that the input codecs are supported: see [[ERROR] BAD/MISSING LINK TEXT](inputs-supported-containers.md)\. Make sure the captions formats are supported [[ERROR] BAD/MISSING LINK TEXT](supported-captions.md)\.

+ AWS Elemental MediaLive requires redundant sources, so you must provide two video streams\. For optimized redundancy, AWS Elemental MediaLive runs each source on different encoders in different Availability Zones \(AZs\)\. 

  The two streams must be identical in terms of resolution and bit rate\. The streams need not be completely synchronized: AWS Elemental MediaLive will accept them if they are not\. But AWS Elemental MediaLive will not adjust the streams in order to synchronize them\. If an input failure occurs and AWS Elemental MediaLive fails over to the redundant input, then the output maybe skip or repeat\. 

+ For a push input, keep in mind that the input needs to be ready when you start the associated channel\. It does not need to be pushing before then\. 

+ For a push input, determine the IP addresses the two streams will be pushing from and make a note of them\. You will need this information in order to set up the required input security groups for the AWS Elemental MediaLive inputs that you will create\.

+ For a pull input, keep in mind that the input needs to be ready to be pulled at the moment that you create the associated channel\. It must be ready at this point because AWS Elemental MediaLive verifies that the input can be accessed\. 