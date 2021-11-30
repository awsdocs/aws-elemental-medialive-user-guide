# How to read the supported captions information<a name="how-to-read-the-support-information"></a>

With captions, there are constraints on the ability to produce a specific output format from the input format\. 

You must make sure it is possible to produce the output formats that you want in a specific output type, from the captions in the input\. For example, you must make sure that you can produce DVB\-Sub captions in an Archive output, when the source is an HLS input that contains SCTE\-20 captions\.

To determine that the input type and input captions format can produce the chosen captions format in the chosen output type, consult the tables in the following [sections](supported-formats-archive-output.md)\.

Follow these steps

1. Find the table for your output container\. For example, Archive\.

1. In that table, look in the first column for the container type of the input that you have been provided with\. For example, HLS\.

1. In the second column, find the input captions that are in that container\. For example, SCTE\-20\.

1. In the third column, look for the output captions format that you require\. For example, DVB\-Sub\.

   If the format is listed, then your input is suitable\.

   If the format is not listed, you must ask the provider of that input to provide a different source\.

The tables for the supported formats are in the following sections:
+ [Formats supported in an Archive output](supported-formats-archive-output.md)
+ [Formats supported in an HLS output or a MediaPackage output](supported-formats-hls-output.md)
+ [Formats supported in a Microsoft Smooth output](supported-formats-smooth-output.md)
+ [Formats supported in an RTMP output](supported-formats-rtmp-output.md)
+ [Formats supported in a UDP output or a multiplex output](supported-formats-ts-output.md)