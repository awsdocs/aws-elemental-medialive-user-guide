# Step 2: Complete the fields on the console<a name="hls-specify-destination-emp"></a>

After you have designed the output names and destination paths, you can set up the HLS output group\.

The following fields configure the location and names of the HLS media and manifest files \(the destination\)\.
+ **Output group – HLS group destination** section
+ **Output group – HLS settings – CDN** section
+ **Output group – Location – Directory structure **
+ **Output group – Location – Segments per subdirectory**
+ **HLS outputs – Output settings – Name modifier**
+ **HLS outputs – Output settings – Segment modifier**

**To set the destination for most downstream systems**

1. Complete the **URL** fields in the **HLS group destinations** section\. Specify two destinations if the channel is set up as a standard channel, or one destination if it is set up as a single\-pipeline channel\.     
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/hls-specify-destination-emp.html)

1. Enter the input user name\. For the password, enter the name of the password stored on the AWS Systems Manager Parameter Store\. Don't enter the password itself\. For more information, see [Requirements for AWS Systems Manager—creating password parameters in parameter store ](requirements-for-EC2.md)\.

1. In the **CDN** settings section, choose `Hls webdav`\.

1. If the downstream system gave you values to [configure the connection](origin-server-http.md), enter those values in the fields in the **CDN** settings section\.