# Examples of destination fields for an archive output group<a name="archive-examples"></a>

These examples show how to set up the fields that relate to file locations\. They don't show how to set up other fields such as fields in the individual outputs\.

## Example 1<a name="archive-example-1"></a>

You want to create an archive of the streaming output from TV channel 59\. You want to store the output in the S3 bucket named **DOC\-EXAMPLE\-BUCKET**, and you want to break up the stream into 5\-minute chunks\.


| Field | Value | 
| --- | --- | 
| Rollover interval field in Archive settings section | 300 | 
| URL in Archive group destination A section | s3ssl://DOC\-EXAMPLE\-BUCKET/channel59/delivery/curling | 
| URL in Archive group destination B section | s3ssl://DOC\-EXAMPLE\-BUCKET/channel59/backup/curlingUsing *delivery* and *backup* as folder names is only an example\. | 
| Name modifier in Archive outputs section | \-$dt$For information about identifiers for variable data \(such as `$dt$`\), see [Reference: identifiers for variable data](variable-data-identifiers.md)\. | 
| Extension in Archive outputs section | Leave blank to use the default \(\.m2ts\)\. | 

Result: the output will be broken into files of 5 minutes \(300 seconds\) each\. Each file will have a file name of **curling**, the time that the channel started and a counter \(000000, 000001, and so on\), and the file name extension\. For example:
+ The first file will be **curling\-20171012T033162\-000001\.m2ts**\.
+ The second file will be **curling\-20171012T033162\-000002\.m2ts**\.

Each file will be stored in both **s3ssl://DOC\-EXAMPLE\-BUCKET/channel59/delivery** and **s3ssl://DOC\-EXAMPLE\-BUCKET/channel59/backup**\. 

A given file is not visible in Amazon S3 while it is being written\. As soon as the rollover happens \(or if the user stops the channel\), MediaLive closes the current file\. At that point, the file becomes visible\.

## Example 2<a name="archive-example-3"></a>

You want to create an archive of highlights from the curling game that are also being streamed \(in a separate HLS output group\)\. You want to create three outputs: one that has audio languages for Europe, one for audio languages for Asia, and one for audio languages for Africa\. You want to store the outputs in the S3 buckets named **DOC\-EXAMPLE\-BUCKET1** and **DOC\-EXAMPLE\-BUCKET2**\. You want to break up the stream into 5 minute chunks\. 


| Field | Value | 
| --- | --- | 
| Rollover interval field in Archive settings section | 300 | 
| URL in Archive group destination A section | s3ssl://DOC\-EXAMPLE\-BUCKET1/sports\-delivery/highlights/curling/10312017In this example, the **10312017** folder is set to match today's date\. | 
| URL in Archive group destination B section | s3ssl://DOC\-EXAMPLE\-BUCKET2/sports\-delivery/highlights/curling/10312017In this example, the paths have different bucket names\. | 
| Name modifier in Archive outputs section |  Choose **Add output** twice: two more **Output** lines are added to this section, for a total of three lines\. In each line, enter a modifier: **\-audiogroup1**, **\-audiogroup2**, and **\-audiogroup3**\.  | 
| Extension in Archive outputs section | Leave blank to use the default \(\.m2ts\)\. | 

Result: three separate categories of files are created for each output\. Each file has a file name of **10312017**, plus the modifier, the sequential counter, and the file name extension\. For example:
+ `10312017-audiogroup1-000000.m2ts`, `10312017-audiogroup2-000000.m2ts`, and `10312017-audiogroup3-000000.m2ts`\. 
+ `10312017-audiogroup1-000001.m2ts`, `10312017-audiogroup2-000001.m2ts`, and `10312017-audiogroup3-000001.m2ts`\. 

Each file will be stored in both `s3ssl://DOC-EXAMPLE-BUCKET1/sports-delivery/highlights/curling` and `s3ssl://DOC-EXAMPLE-BUCKET2/sports-delivery/highlights/curling`\.

A given file is not visible in Amazon S3 while it is being written\. As soon as the rollover happens \(or if the user stops the channel\), MediaLive closes the current file\. At that point, the file becomes visible\.
