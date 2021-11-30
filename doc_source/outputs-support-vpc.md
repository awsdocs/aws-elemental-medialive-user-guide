# Support for delivery to VPC<a name="outputs-support-vpc"></a>

The following table specifies which containers can be delivered to a destination in the VPC, when the channel that is set up for VPC delivery\. For more information about VPC delivery, see [Delivering outputs via your VPC](delivery-out-vpc.md)\. 


| MediaLive output type \(output group\) | Can be delivered to a destination in your VPC | Can be delivered to a destination outside your VPC | 
| --- | --- | --- | 
| Archive | A bucket, if Amazon S3 is set up with a VPC endpoint | Yes, if you associate Elastic IP addresses with the channel | 
| Frame Capture | A bucket, if Amazon S3 is set up with a VPC endpoint | Yes, if you associate Elastic IP addresses with the channel | 
| HLS to an HTTP or HTTPS server | A bucket, if Amazon S3 is set up with a VPC endpoint | Yes, if you associate Elastic IP addresses with the channel | 
| HLS to an Akamai server | A bucket, if Amazon S3 is set up with a VPC endpoint | Yes, if you associate Elastic IP addresses with the channel | 
| HLS to MediaPackage, over HTTP | No | Yes, if you associate Elastic IP addresses with the channel | 
| HLS to MediaStore | No | Yes, if you associate Elastic IP addresses with the channel | 
| HLS to Amazon S3 | A bucket, if Amazon S3 is set up with a VPC endpoint | Yes, if you associate Elastic IP addresses with the channel | 
| MediaPackage | No | Yes, if you associate Elastic IP addresses with the channel | 
| Microsoft Smooth | A server on Amazon EC2 | Yes, if you associate Elastic IP addresses with the channel | 
| Multiplex | NoWhen the channel is set up for VPC delivery, it can't contain a multiplex output\. | NoWhen the channel is set up for VPC delivery, it can't contain a multiplex output\. | 
| RTMP or RTMPS | A server on Amazon EC2 | Yes, if you associate Elastic IP addresses with the channel | 
| UDP | A server on Amazon EC2 | Yes, if you associate Elastic IP addresses with the channel | 