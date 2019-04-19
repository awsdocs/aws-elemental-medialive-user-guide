# Enabling Manifest Decoration in the Output<a name="enable-manifest-decoration"></a>

You can choose to interpret SCTE\-35 messages from the original input and insert corresponding instructions into the output manifest for the following outputs:
+ HLS
+ Microsoft Smooth \(the instructions are inserted in the sparse track\)\.

MediaPackage outputs, which are a type of HLS output, are set up with manifest decoration enabled\. You can't disable decoration in these outputs\.

Manifest decoration is enabled at the output group level\. If you enable the feature in a specific output group, all the outputs in that group have their manifests decorated\.

To include manifest decoration in some outputs and not others, you must create two output groups of the specified type, for example, two HLS output groups\.

**Topics**
+ [Enabling Decoration – HLS](procedure-to-enable-decoration-hls.md)
+ [Enabling Decoration – Microsoft Smooth](procedure-to-enable-decoration-ms-smooth.md)
+ [How SCTE\-35 Events Are Handled in Manifests and Sparse Tracks](how-scte-35-events-are-handled-in-manifests.md)