# Organize encodes in an RTMP output group<a name="design-rtmp-package"></a>

An RTMP output group contains one video encode, one audio encode, and one captions encode\.

Plan for the output group to contain one output that holds all the encodes\. 

This diagram illustrates an RTMP output group where the captions are embedded in the video encode\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output1-non-abr-Ve-A.png)

This diagram illustrates an RTMP output group with object\-style captions\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output2-non-abr-VAC.png)