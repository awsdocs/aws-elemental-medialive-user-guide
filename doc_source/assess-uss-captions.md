# Assess captions<a name="assess-uss-captions"></a>

If you plan to include captions in an output group, you must determine if MediaLive can use the captions format in the source to produce the captions format that you want in the output\. 

Obtain the following information about the captions source\.


****  
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/assess-uss-captions.html)

**To assess the captions requirements**

Follow these steps for each [output group that you identified](identify-downstream-system.md) for your workflow\.

1. Go to [Reference: supported captions](supported-captions.md) and find the section for the output group\. For example, find [Formats supported in an HLS output or a MediaPackage output](supported-formats-hls-output.md)\. In the table in that section, read down the first column to find the format \(container\) that the content provider is providing\. 

1. Read across to the *Source caption input* column to find the caption formats that MediaLive supports in that source format\.

1. Then read across to the *Supported output captions* column to find the caption formats that MediaLive can convert the source format to\.

   You end up with a statement such as: "If you want to produce an HLS output and your source content is RTMP, you can convert embedded captions to burn\-in, embedded, or WebVTT"\.

1. Verify that the source content from the content provider matches one of the formats in the *Supported caption input* column of the table\. For example, verify that the source content contains embedded captions\.

1. Find the list of captions formats that the downstream system supports\. You obtained this list when you [identified the encode requirements for the output groups that you identified](identify-dss-video-audio.md)\. Verify that at least one of these output formats appears in the *Supported output captions* column of the table\.

   If there is no match in the source content, or no match in the output, then you can't include captions in the output\.

For example, assume that you need to produce an HLS output group\. Assume that your content provider can give you content in RTP format with embedded captions\. Assume that the downstream system requires that for HLS output, the output must include WebVTT captions\.

Following the steps above, you read the table for HLS outputs\. In the container column of the table, you find the row for RTP format\. You read across to the source column and identify that embedded captions are a supported source format\. You then read across to the output column and find that embedded captions can be converted to burn\-in, embedded, or WebVTT captions\. WebVTT captions is the format that the downstream system requires\. Therefore, you conclude that you can include captions in the HLS output\.