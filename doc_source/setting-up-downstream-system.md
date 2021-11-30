# Step 7: Arrange for delivery to downstream systems<a name="setting-up-downstream-system"></a>

As the final step in preparing the downstream and upstream systems in your workflow, you must perform this step on each downstream system:
+ You and the operator at the downstream system must agree on some portions of the path from AWS Elemental MediaLive to the downstream system\.
+ You must arrange for the operator at the downstream system to perform some setup so that MediaLive can successfully send outputs to these systems\.

The setup is different for each type of output group and downstream system\. 

The *output* from MediaLive is considered *input* to this downstream system\. You and the operator of the downstream system must agree about the input locations on the downstream system now, because when you create the MediaLive channel you need those URL locations\. 

Note that this guide describes how to set up an origin server\. It does not describe how to set up the CDN that is downstream of the origin server\. For information about that setup, see the documentation for the chosen origin server\.

**The options**  
The following table summarizes the combinations of output group and downstream system that are covered in the following sections\.


****  

|  Output group   |  Downstream system  |  Section to read  | 
| --- | --- | --- | 
| Archive | Amazon S3 |  [Archive or frame capture output group](origin-server-s3.md)  | 
| Frame capture | Amazon S3 |  [Archive or frame capture output group](origin-server-s3.md)  | 
| HLS | Amazon S3 |  [HLS output group to Amazon S3](origin-server-hls-s3.md)  | 
| HLS | AWS Elemental MediaStore |  [HLS output group to MediaStore](origin-server-ems.md)  | 
| HLS | AWS Elemental MediaPackage  |  [HLS output group to MediaPackage](origin-server-hls-emp.md)  | 
| HLS | HTTP server or Akamai CDN |  [HLS output group to HTTP](origin-server-http.md)  | 
| MediaPackage | AWS Elemental MediaPackage |  [MediaPackage output group](origin-server-emp.md)  | 
| Microsoft Smooth | HTTP server |  [Microsoft Smooth output group](origin-server-mss.md)  | 
| RTMP | RTMP server |  [RTMP output group](origin-server-rtmp.md)  | 
| UDP | UDP address |  [UDP output group](downstream-system-udp.md)  | 

**Result of this step**  
At the end of this step, you will have completed all the steps to prepare the downstream system to receive content from MediaLive\.

**Topics**
+ [Archive or frame capture output group](origin-server-s3.md)
+ [HLS output group to Amazon S3](origin-server-hls-s3.md)
+ [HLS output group to MediaStore](origin-server-ems.md)
+ [HLS output group to MediaPackage](origin-server-hls-emp.md)
+ [HLS output group to HTTP](origin-server-http.md)
+ [MediaPackage output group](origin-server-emp.md)
+ [Microsoft Smooth output group](origin-server-mss.md)
+ [RTMP output group](origin-server-rtmp.md)
+ [UDP output group](downstream-system-udp.md)