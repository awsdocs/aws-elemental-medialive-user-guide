# Organize encodes in an Archive output group<a name="design-archive-package"></a>

An Archive output group can contain one video encode, one or more audio encodes, and one or more captions encodes \(either [embedded or object\-style\)](categories-captions.md)\.

Plan for the output group to contain one output that contains all the encodes\. 

This diagram illustrates an Archive output group that contains one output that holds one video encode with embedded captions, and two audio encodes\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output3-nonABR-Ve-2A.png)

This diagram illustrates an Archive output group that contains one output that holds one video encode, two audio encodes, and two object\-style captions encode\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/output4-nonABR-V-2A-2C.png)