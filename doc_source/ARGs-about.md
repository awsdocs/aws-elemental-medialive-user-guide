# About audio rendition groups<a name="ARGs-about"></a>

## Standards compliance<a name="ARG-compliance"></a>

This implementation of audio rendition groups is compliant with *HTTP Live Streaming draft\-pantos\-http\-live\-streaming\-18* section 4\.3\.4\.1\.1\. 

## Examples<a name="ARG-examples"></a>

### Example 1<a name="ARGs-example-1"></a>

The HLS output group consists of:
+ One video output\.
+ Three audio outputs \(perhaps English, French, Spanish\) that all belong to the same audio rendition group\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/ARG_oneV_threeA.png)

### Example 2<a name="ARG-example-2"></a>

The HLS output group consists of:
+ One *video high* output\.
+ One *video medium* output\.
+ One *video low* output\.
+ Three audio outputs \(English, French, Spanish\) that all belong to the same audio rendition group\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/ARG_threeV_threeA.png)

### Example 3<a name="ARG-3"></a>

The HLS output group consists of:
+ One *video high* output\.
+ One *video low* output\.
+ Two audio outputs \(English, French\) that each use the AAC codec\. These outputs both belong to the same audio rendition group, RG1\. 
+ Two audio outputs \(English, French\) that each use the Dolby Digital codec\. These outputs both belong to the same audio rendition group, RG2\. 
+ The video high output is associated with both audio rendition groups\.
+ The video low output is associated only with the RG1 audio rendition group\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/ARG_twoV_twoA.png)