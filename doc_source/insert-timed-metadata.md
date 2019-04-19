# Inserting ID3 Metadata When Creating the Channel<a name="insert-timed-metadata"></a>

You can set up to insert ID3 metadata at a regular cadence \(for example, every 10 seconds\) into HLS or UDP outputs where you enabled ID3 metadata\. You can't insert ID3 metadata into Archive or MediaPackage outputs\. 

**To insert ID3 metadata when creating the channel**

1. Make sure that you enabled ID3 metadata\. For detailed information, see [Enabling ID3 Metadata](enable-passthrough-id3.md)\.

1. On the **Create channel** page, in the **Output groups** section, choose the HLS group or the UDP group\. \(You can't insert ID3 metadata in an Archive group or MediaPackage group\.\)

1. Choose **ID3**\.

1. For **Timed Metadata ID3 Frame**, choose the ID3 frame type that you want to apply to the metadata\.

   Try to avoid using PRIV for metadata that you insert when creating the channel and for metadata from one of the other sources\. 

1. For **Timed Metadata ID3 Period**, enter the repeat interval for the ID3 metadata, in seconds\.

   For a UDP output group, set any length\. For an HLS output group, we recommend that you set the period \(interval\) to half the segment length\. To verify the segment length, in the **HLS output group**, choose **Manifests and Segments**, and look at **Segment Length**\. 

When you start the channel, the first ID3 metadata is inserted shortly after the output starts and then at the specified interval for the lifetime of the channel\.

The timestamp in the ID3 metadata is derived from the output timecode\. It indicates the time at which the ID3 frame is inserted into the output, when the channel is running\. The timestamp is in the format that you specified for the **Source** field in the **Timecode Configuration** section of the **General Settings** page for the channel\.