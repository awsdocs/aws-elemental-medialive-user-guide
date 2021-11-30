# Organize encodes in an HLS or MediaPackage output group<a name="design-hls-package"></a>

An HLS or MediaPackage output group is typically set up as a video ABR stack\. The term *ABR* stands for *adaptive bitrate*\. A video *ABR stack* is an output group that contains the following:
+ Multiple versions \(renditions\) of the video\. Each rendition has a different resolution\. 
+ One or more audio encodes\.
+ One or more captions encodes\.

There are two ways to organize the encodes, depending on whether the audio encodes must be bundled or each in their own rendition\. You should have already [obtained this information](identify-dss-video-audio.md) from your downstream system\.

**Downstream players that require bundled audio**  
Plan for the output group to contain the following:
+ One output for each video encode\. This output holds one video encode, all the audio encodes, and all the captions encodes \(if the captions are embedded\)\. 

  The same audio encodes will appear in each output\. For example, the English and French encodes will appear in the high\-resolution output, then the same English and French encodes will appear in the low\-resolution output\.
+ One output for each captions encode, if the captions are sidecars\.

This diagram illustrates an HLS output group when the captions encodes are embedded\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output11-ABR-2Ve-2A.png)

This diagram illustrates an HLS output group when the captions encodes are sidecars\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output12-ABR-2V-2A-2C.png)

**Downstream players that require separate audio**  
Plan for the output group to contain the following:
+ One output for each video encode\. This output holds one video and all the captions encodes \(if the captions are embedded\)\. 
+ One output for each audio encode\.

  The audio encodes might be for different languages, or they might be for different bitrates, or they might be for different languages and bitrates\.
+ One output for each captions encode, if the captions are sidecars\.

The arrangement of the audio encodes in this output group is called an *audio rendition group*\.

This diagram illustrates an HLS output group with an audio rendition group, and with embedded captions encodes\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output13-ABR-2Ve-2Asep.png)

This diagram illustrates an HLS output group for an ABR stack with an audio rendition group, and with sidecar captions encodes\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output14-ABR-2V-2Asep-2C.png)