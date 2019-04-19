# Enabling ID3 Metadata<a name="enable-passthrough-id3"></a>

To include ID3 metadata in an output, you must enable ID3 metadata in that output when you create or edit the channel\. 

## Enabling in Archive Outputs<a name="enable-passthrough-archive"></a>

To include ID3 metadata in Archive outputs, you must enable the feature in each applicable output\. 

**To enable ID3 metadata in Archive outputs**

1. On the **Create channel** page, in the **Output groups** section, in the **Archive** group, choose the output where you want to enable ID3 metadata\. 

1. For **Container Settings**, for **PID Settings**, for **Timed Metadata Behavior**, choose **PASSTHROUGH**\.

1. For **Timed Metadata PIDs**, enter the PID where you want to insert the ID3 metadata\.

1. Repeat for each applicable output\.

For information about the results of enabling, see [Results of Enabling ID3 Metadata](#id3-enable-result) later in this section\.

## Enabling in HLS Outputs<a name="enable-passthrough-hls"></a>

To include ID3 metadata in HLS outputs, you must enable the feature in each applicable output\. 

**To enable ID3 metadata in HLS outputs**

1. On the **Create channel** page, in the **Output groups** section, in the **HLS** group, choose the output where you want to enable ID3 metadata\. 

1. Make sure that **HLS Settings** is set to **Standard hls**\. Only standard outputs can contain ID3 metadata\. The **Audio\-only outputs** option \(which is the other option in this field\), is used to set up audio rendition groups and can't contain this metadata\.

1. For **PID Settings**, **Timed Metadata Behavior**, choose **PASSTHROUGH**\.

1. For **Timed Metadata PIDs**, enter the PID where you want to insert the ID3 metadata\.

1. Repeat for each applicable output\.

For information about the results of enabling, see [Results of Enabling ID3 Metadata](#id3-enable-result) later in this section\.

## Enabling in MediaPackage Outputs<a name="enable-passthrough-mediapackage"></a>

To include ID3 metadata in MediaPackage outputs, you don't have to set up the output\. MediaPackage outputs are automatically set up with this feature enabled\. 

For information about handling of ID3 metadata in MediaPackage outputs, see [Results of Enabling ID3 Metadata](#id3-enable-result) later in this chapter\.

## Enabling in UDP Outputs<a name="enable-passthrough-udp"></a>

To include ID3 metadata in UDP outputs, you must enable the feature in each applicable output\. 

**To enable ID3 metadata in UDP outputs**

1. On the **Create channel** page, in the **Output groups** section, in the **UDP** group, choose the output where you want to enable ID3 metadata\. 

1. For **Network Settings**, **PID Settings**, **Timed Metadata Behavior**, choose **PASSTHROUGH**\.

1. For **Timed Metadata PIDs**, enter the PID where you want to insert the metadata\.

1. Repeat for each applicable output\.

For information about the results of enabling, see [Results of Enabling ID3 Metadata](#id3-enable-result) later in this section\.

## Results of Enabling ID3 Metadata<a name="id3-enable-result"></a>

Here are the results of enabling ID3 metadata in the channel:
+ ID3 metadata other than type TDRL or PRIV that is present in the input is automatically included in the eligible outputs\. 
+ ID3 metadata of type TDRL or PRIV that is present in the input is passed through to eligible outputs as follows:
  + If the frame doesn't have "Elemental Technologies" included in the wording, the metadata is passed through\.
  + If the frame has "Elemental Technologies" included in the wording, the metadata is not passed through\. The metadata isn't passed through because MediaLive assumes that the timestamp for this metadata has passed\.
+ ID3 metadata that you set up in the output group is inserted in those outputs where you enabled ID3 metadata, when you created the channel\. For information about setting up ID3 metadata in the output group, see [Inserting ID3 Metadata When Creating the Channel](insert-timed-metadata.md)\.
+ ID3 metadata that you set up by creating an action in the MediaLive schedule is included in the eligible outputs\. For information about setting up ID3 metadata in the schedule, see [ Inserting ID3 Metadata Using the Schedule](insert-usercreated-metadata.md)\.

The eligibility of an output depends on the output group type, as shown in the following table\.


| Type of Output Group | ID3 Metadata That Is Present in Input | ID3 Metadata That You Specify When Setting Up the Channel | ID3 Metadata That You Insert Using the Schedule | 
| --- | --- | --- | --- | 
| Archive | Passed through | Not included in output | Included in output | 
| HLS | Passed through | Included in output | Included in output | 
| MediaPackage | Passed through | Not included in output | Included in output | 
| UDP | Passed through | Included in output | Not included in output | 