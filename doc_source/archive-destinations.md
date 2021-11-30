# Fields for the output destination<a name="archive-destinations"></a>

The following fields configure the location and names of the archive output files \(the destination\)\.
+ **Output group** – **Archive group destination** section
+ **Output group** – **Archive settings** – **CDN settings**
+ **Output group** – **Additional settings** – **Rollover interval**
+ **Archive outputs** – **Name modifier**
+ **Archive outputs** – **Extension**

You must design the destination path or paths for the output\. You must then enter the different portions of the path into the appropriate fields on the console\. 

## Design the path for the output destination<a name="archive-about-destination-path"></a>

As part of the planning for this output group, you [discussed your requirements](origin-server-s3.md) with the Amazon S3 user\. You should already have the following information:
+ The bucket names portion of the path for the output
+ Or the full path for the output\.

**To design the path**

If you haven't yet designed the destination path, design them now\. If you've already designed the paths, go to [Complete the fields on the console](#archive-specify-destination)\.
+ Design the destination path or paths, following this syntax:

  `protocol bucket folders baseFilename nameModifier counter extension`

  For example, for a standard channel:

  `s3ssl://DOC-EXAMPLE-BUCKET/channel59/delivery/curling-20171012T033162.000000.m2ts`

  `s3ssl://DOC-EXAMPLE-BUCKET1/channel59/delivery/curling-20171012T033162.000000.m2ts`

The following table maps each portion in the example to the portion in the syntax\.


| Portion of the URL | Example | Comment | 
| --- | --- | --- | 
| protocol | s3ssl:// | The protocol is always s3ssl:// because the destination for an Archive output is always an S3 bucket\. | 
| bucket portion of the path | DOC\-EXAMPLE\-BUCKET | When you [planned the workflow for the channel](origin-server-s3.md), you should have made sure that the S3 bucket or buckets exist\.With MediaLive, the S3 bucket name must not use dot notation\. For example, **mycompany\-videos** is acceptable but **mycompany\.videos** isn't\.  | 
| folders portion of the path | channel59/delivery/ | The folders can be present or not, and can be as long as you want\.The folders must always end with a slash\. | 
| baseFilename | curling | Don't terminate the file name with a slash\. | 
| nameModifier | \-20171012T033162 | The modifier is optional for an archive output\. | 
| delimiter before the counter | \. | MediaLive automatically inserts this delimiter\. | 
| counter | 000000 | MediaLive automatically generates this counter\. Initially, this is a six\-digit number starting at 000000, and increasing by 1\. So 000000, 000001, 000002 and so on\. After 999999, the next number is 1000000 \(seven digits\), then 1000001, 1000002, and so on\. Then from 9999999 to 10000000 \(eight digits\), and so on\. | 
| dot before the extension | \. | MediaLive automatically inserts this dot\. | 
| extension | m2ts | Always m2ts\. | 

## Complete the fields on the console<a name="archive-specify-destination"></a>

**To specify the location for the output**

1. Enter the different portions of the destination in the appropriate fields\.     
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/archive-destinations.html)

1. Leave the **Credentials** section blank in both the **Archive group destinations** sections\. MediaLive has permission to write to the S3 bucket via the trusted entity\. Someone in your organization should have already set up these permissions\. For more information, see [Reference: summary of requirements for the MediaLive trusted entity](trusted-entity-requirements.md)\.

1. Complete the **CDN settings** field only if MediaLive must set a canned ACL whenever it sends this output to the Amazon S3 bucket\.

   Use of a canned ACL typically only applies if your organization is not the owner of the Amazon S3 bucket\. You should have discussed the use of a canned ACL with the bucket owner when you discussed the [destination for the output](origin-server-s3.md#setting-dss-archive-canned-acl)\.

1. Complete the **Rollover interval** field in the **Archive settings** section\.

   For example, **300** divides the output into separate files, each with a 300 second \(5 minutes\) long duration\. 

   Each time the rollover expires, MediaLive closes the current file on Amazon S3 and starts a new file using the `baseFilename`, the `nameModifier`, and a sequential counter\. 

   The current file is visible on Amazon S3 only after it has closed\.

For more information, see the [examples](archive-examples.md)\. 