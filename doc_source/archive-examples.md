# Archive Examples<a name="archive-examples"></a>

These examples show how to set up the fields that relate to locations\. They don't show how to set up other fields such as fields in the individual outputs\.

## Example 1<a name="archive-example-1"></a>

You want to create an archive of the streaming output from TV channel 59\. You want to store the output in the S3 bucket named "channel59", and you want to break up the stream into 10\-minute chunks\.


| Field | Value | 
| --- | --- | 
| Rollover interval field in Archive settings section | 600 | 
| URL in Archive group destination A section | s3ssl://channel59/delivery/program | 
| URL in Archive group destination B section | s3ssl://channel59/backup/programUsing "delivery" and "backup" as folder names is only an example\. | 
| Name modifier in Archive outputs section | \_$dt$For information about identifiers for variable data \(such as `$dt$`\), see [Reference: Identifiers for Variable Data](variable-data-identifiers.md) | 
| Extension in Archive outputs section | Leave blank to use the default \(\.ts\)\. | 

Result: the output will be broken into files of 10 minutes \(600 seconds\) each\. Each file will have a file name of `program`, plus the time that the channel started plus a counter \(000000, 000001, and so on\), plus the file name extension\. For example:
+ The first file will be `program_20171012T033162.000000.ts`\.
+ The second file will be `program_20171012T033162.000001.ts`\.

Each file will be stored in both `s3ssl://channel59/delivery` and `s3ssl://channel59/backup`\. 

A given file is not visible in Amazon S3 while it is being written\. As soon as the rollover happens \(or if the user stops the channel\), MediaLive closes the current file\. At that point, the file becomes visible\.

## Example 2<a name="archive-example-3"></a>

You want to create an archive of highlights from the curling game that are also being streamed \(in a separate HLS output group\)\. You want to create three outputs: one that has audio languages for Europe, one for audio languages for Asia, and one for audio languages for Africa\. You want to store the outputs in the Amazon S3 bucket named "sports/highlights/curling"\. You want to break up the stream into five\-minute chunks\. 


| Field | Value | 
| --- | --- | 
| Rollover interval field in Archive settings section | 300 | 
| URL in Archive group destination A section | s3ssl://sports/delivery/highlights/curling/10312017In this example, the **10312017** folder is set to match today's date\. | 
| URL in Archive group destination B section | s3ssl://sports/backup/highlights/curling/10312017Using "delivery" and "backup" as folder names is only an example\. | 
| Name modifier in Archive outputs section |  Choose **Add output** twice: two more **Output** lines are added to this section, for a total of three lines\. In each line, enter a modifier: **\_audiogroup1**, **\_audiogroup2**, and **\_audiogroup3**\.  | 
| Extension in Archive outputs section | Leave blank to use the default \(\.ts\)\. | 

Result: three separate sets of files are created for each output\. Each file has a file name of `10312017`, plus the modifier, plus the sequence counter, plus the file name extension\. For example:
+ `10312017_audiogroup1.000000.ts`, `10312017_audiogroup2.000000.ts`, and `10312017_audiogroup3.000000.ts`\. 
+ `10312017_audiogroup1.000001.ts`, `10312017_audiogroup2.000001.ts`, and `10312017_audiogroup3.000001.ts`\. 

Each file will be stored in both `s3ssl://sports/delivery/highlights/curling` and `s3ssl://sports/backup/highlights/curling`\.

A given file is not visible in Amazon S3 while it is being written\. As soon as the rollover happens \(or if the user stops the channel\), MediaLive closes the current file\. At that point, the file becomes visible\.