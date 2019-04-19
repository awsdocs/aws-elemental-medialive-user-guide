# Working with ID3 Metadata<a name="id3-metadata"></a>

You can include ID3 metadata in Archive outputs, HLS outputs, MediaPackage outputs, and UDP outputs\. Typically, you include ID3 metadata in an output if you know that a downstream system expects the data and is capable of interpreting it\. 

You should obtain the requirements for ID3 metadata from a representative of the downstream system\.

When you are creating or editing a channel, you can set up individual outputs in a channel so that ID3 metadata is enabled\. The ID3 metadata can come from one or more of the following sources:
+ It can be metadata that is already present in the input\.
+ It can be metadata that you add when you create the channel\.
+ It can be metadata that you add by creating actions in the schedule\.

ID3 metadata is included in the Archive, HLS, MediaPackage, or UDP output according to the [specific rules](enable-passthrough-id3.md#id3-enable-result) for the output type\. 

**Topics**
+ [Enabling ID3 Metadata](enable-passthrough-id3.md)
+ [Passing Through ID3 Metadata](passthru-metadata.md)
+ [Inserting ID3 Metadata When Creating the Channel](insert-timed-metadata.md)
+ [Inserting ID3 Metadata Using the Schedule](insert-usercreated-metadata.md)