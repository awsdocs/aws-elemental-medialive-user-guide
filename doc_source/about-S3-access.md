# Access to Amazon S3<a name="about-S3-access"></a>

Your deployment may include using files in an Amazon S3 bucket\. For example:

+ The source for an HLS input\.

+ The destination for an Archive output group\.

+ The destination for an HLS output group\.

In all these cases, regardless of whether the connection is secure or not, AWS Elemental MediaLive must have a trusted entity role that includes Amazon S3\. See [[ERROR] BAD/MISSING LINK TEXT](trusted-entity-role.md)\.