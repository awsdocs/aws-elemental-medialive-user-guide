# Overview of multiplex and MPTS in AWS Elemental MediaLive<a name="mpts-general"></a>

A multi\-program transport stream \(MPTS\) is a UDP transport stream \(TS\) that carries multiple programs\. AWS Elemental MediaLive lets you create an MPTS that contains all variable bitrate programs, a mix of variable and constant bitrate programs, or all constant bitrate programs\. 

To create an MPTS, you create a MediaLive multiplex\. You then add up to 20 MediaLive programs to the multiplex\. Finally, you create one MediaLive channel for each program, and associate each channel with its program\. 

**Channel** 

The channel is a regular MediaLive channel that is configured in a specific way\. The channel is dedicated to a multiplex, which means that you can't use it to produce both an MPTS output and other outputs \(such as SPTS UDP or HLS outputs\)\. 

Supported sources are those that use a MediaConnect input or an MP4 input\. 

The channel contains only one output group, of type **Multiplex**, and one output\. This output is a transport stream\. Apart from these special requirements for the input and output, the channel is like any regular channel\. For the video, audio, and captions that it produces, it follows the rules for a UDP output\. 

The channel is always a standard channel\. It can include any of the regular channel features that you can implement for a UDP output, such as input switching and SCTE\-35 ad avails messages\.

**Program**

The channel is attached to a MediaLive program\. 

The program provides information about the bitrate for the video in this program\. Each program can have a constant video bitrate, or it can have a variable video bitrate\. For a variable video bitrate, the multiplex allocates the bitrate for the program based on the demands of all the programs\.

**Multiplex **

Each program is attached to the multiplex\. A multiplex can contain up to 20 programs\. 

The MediaLive multiplex provides configuration information for the MPTS, including the bitrate of the entire MPTS\. 

**Starting a Multiplex**

When you are ready, you start the multiplex and the channels\. \(You don't start the programs\.\) 

The MPTS is an RTP output\. MediaLive creates and delivers the MPTS to AWS Elemental MediaConnect in the account associated with the MediaLive that is creating the MPTS\. AWS Elemental MediaConnect automatically sets up the RTP output as an entitled source\. You don't have to perform any steps to set up this entitled source\. But in order to complete the distribution of the MPTS, you must create a flow that uses that entitled source\.

For more information about starting the multiplex, see [Starting, pausing, or stopping a multiplex](start-pause-stop-multiplex.md)\. For more information about entitled sources, see [Creating a Flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-create.html) in the *AWS Elemental MediaConnect User Guide*\.