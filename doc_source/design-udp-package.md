# Organize encodes in a UDP output group<a name="design-udp-package"></a>

A UDP output group can contain one video encode, one or more audio encodes, and one or more captions encodes \(either embedded or object\-style\)\. 

Plan for the output group to contain one output that holds the single video encode, all the audio encodes, and all the captions encodes\. 

This diagram illustrates a UDP output group where the captions are embedded in the video encode\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output3-nonABR-Ve-2A.png)

This diagram illustrates a UDP output group with object\-style captions\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output4-nonABR-V-2A-2C.png)