# SCTE\-35 Passthrough or Removal<a name="scte-35-passthrough-or-removal"></a>

You can set up the AWS Elemental MediaLive channel so that SCTE\-35 messages from the input is passed through \(included\) in the data stream for the following outputs:

+ Outputs in an Archive output group\.

+ Outputs in an HLS output group\.

+ Outputs in a UDP output group\.

**Alignment with Video**  
The PTS of the SCTE\-35 message is adjusted to match the PTS of the corresponding video frame\. 

**Passthrough Is at the Output Level**  
SCTE\-35 passthrough or removal applies at the output level\. The messages are passed through or removed only in a specific output\. The default behavior \(if you do not change the configuration fields\) is to remove the messages\.

## The Procedure for Archive<a name="procedure-to-enable-passthrough-archive"></a>

1. In the channel that you are creating, find the **Archive** output group that contains the output that you want to set up\.

1. Choose that output\.

1. In **PID settings**, complete the following fields:

   + **SCTE\-35 control**: Set to **Passthrough**\.

   + **SCTE\-35 PID**: Leave the default PID or enter the PID where you want the SCTE\-35 messages to go\. 

1. If appropriate, repeat for other outputs in this or other **Archive** output groups\.

All SCTE\-35 messages from the input are included in the data stream of the outputs that you have set up\.

## The Procedure for HLS<a name="procedure-to-enable-passthrough-hls"></a>

1. In the channel that you are creating, find the HLS output group that contains the output that you want to set up\. 

1. Choose that output\.

1. In **PID settings**, complete the following fields:

   + **SCTE\-35 behavior**: Set to **Passthrough**\.

   + **SCTE\-35 PID**: Leave the default PID or enter the PID where you want the SCTE\-35 messages to go\. 

1. If appropriate, repeat for other outputs in this or other HLS output groups\.

All SCTE\-35 messages from the input will be included in the data stream of the outputs that you have set up\.

## The Procedure for UDP<a name="procedure-to-enable-passthrough-udp"></a>

1. In the channel that you are creating, find the UDP output group that contains the output that you want to set up\. 

1. Choose that output\.

1. In **PID settings**, complete the following fields:

   + **SCTE\-35 control**: Set to **Passthrough**\.

   + **SCTE\-35 PID**: Leave the default PID or enter the PID where you want the SCTE\-35 messages to go\. 

1. If appropriate, repeat for other outputs in this or other UDP output groups\.

All SCTE\-35 messages from the input will be included in the data stream of the outputs that you have set up\.