# Enabling Manifest Decoration<a name="enable-manifest-decoration"></a>

You can choose to interpret SCTE\-35 messages from the original input and insert corresponding instructions into the output manifest for the following outputs:

+ HLS

+ Microsoft Smooth \(the instructions are inserted in the sparse track\)\.

Manifest decoration is enabled at the output group level\. If you enable the feature in a given output group, all the outputs in that group have their manifests decorated\.

To include manifest decoration in some outputs and not others, you must create two output groups of the specified type, for example, two HLS output groups\.