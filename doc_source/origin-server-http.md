# HLS output group to HTTP<a name="origin-server-http"></a>

Follow this procedure if you [determined](identify-downstream-system.md) that you will create an HLS output group with one of the following downstream systems as the destination:
+ An HTTP or HTTPS PUT server\.
+ An HTTP or HTTPS WebDAV server\.
+ An Akamai origin server\.

You and the operator of the downstream system must agree about the destination for the output of the HLS output group\. You will need this information when you [create the MediaLive channel](creating-hls-output-group.md)\.

When you deliver HLS over HTTP, you are often delivering to an origin server\. The origin server typically has clear guidelines about the rules for the destination path, including the file name of the main manifest \(the `.M3U8` file\)\.

You must follow the procedure for each HLS output group\.

**To arrange setup of the destination**

You must talk to the operator at the downstream system to coordinate your setup\.

1. If the downstream system isn't an Akamai server, find out if it uses PUT or WebDAV\. 

1. Find out if the downstream system has special connection requirements\. These connection fields are grouped in the console in the **CDN settings** section for the HLS output group\. To display this page on the MediaLive console, in the **Create channel** page, in the **Output groups** section, choose **Add**, then choose **HLS**\. Choose the group, then in **HLS settings**, open **CDN settings**\.

1. Decide if you need two destinations for the output: 
   + You need two destinations for output from a [standard channel](plan-redundancy.md)\.
   + You need one destination for output from a single\-pipeline channel\.

1. Find out if the downstream system uses a secure connection\. If it does, arrange with the operator to set up user credentials\. 

1. Find out if the downstream system requires custom paths inside the main manifests and the child manifests\. For more information, see [Customizing the paths inside HLS manifests](hls-manifest-paths.md)\.

1. If you are setting up a [standard channel](plan-redundancy.md), find out if the downstream system supports redundant manifests\. If so, decide if you want to implement this feature\. For more information, see [Redundant HLS manifests](hls-redundant-manifests.md), and specifically [Rules for most downstream systems](hls-redundant-manif-most-systems.md) and [Rules for Akamai CDNs](hls-redundant-manif-akamai.md) for specific instructions\. 

1. Talk to the operator at the downstream system to agree on a full destination path for the three categories of HLS files \(the main manifests, the child manifests, and the media files\)\. MediaLive always puts all three categories of files for each destination in this one location\. It’s not possible to configure MediaLive to put some files in another location\. 

   If you have two destinations, the destination paths must be different from each other in some way\. At least one of the portions of one path must be different from the other\. It is acceptable for all the portions to be different\. Discuss this requirement with the operator of the downstream system\. The downstream system might have specific rules about uniqueness\.

1. Talk to the operator at the downstream system about special requirements for the names of the three categories of HLS files\. Typically, the downstream system doesn’t have special requirements\. 

1. Talk to the operator at the downstream system about special requirements for the modifier on the names of the child manifests and media files\. 

   The child manifests and media files always include this modifier in their file names\. This modifier distinguishes each output from the other, so it must be unique in each output\. For example, the files for the high\-resolution output must have a different name from the files for the low\-resolution output\. For example, the files for one output could have the file name and modifier `curling_high`, while the other output could have `curling_low`\.

   Typically, the downstream system doesn’t have special requirements\.

1. Ask the operator of the downstream system if the media files should be set up in separate subdirectories\. For example, one subdirectory for the first 1000 segments, another subdirectory for the second 1000 segments, and so on\.

   Most downstream systems don’t require separate subdirectories\.

1. Agree on the portions of the destination path where the downstream system has special requirements\.
   + For example, the downstream system might only require that you send to a specific host\. 

     For example, send to two folders that you name, but on the host at `https://203.0.113.55`

     Or send to two folders that you name, but on the hosts at `https://203.0.113.55` and `https://203.0.113.82`
   + Or the downstream system might require a specific host and folder, but with a file name that you choose\. For example, this host and folders:

     `https://203.0.113.55/sports/delivery/`

     `https://203.0.113.55/sports/backup/`

1. Make a note of the information you have collected:
   + The connection type for the downstream system – Akamai, PUT, or WebDAV\.
   + The settings for connection fields, if the downstream system has special requirements\.
   + The protocol for delivery—HTTP or HTTPS\.
   + The user name and password to access the downstream system, if the downstream system requires authenticated requests\. Note that these user credentials relate to user authentication, not to the protocol\. User authentication is about whether the downstream system will accept your request\. The protocol is about whether the request is sent over a secure connection\.
   + All or part of the destination paths, possibly including the file names\.
   + Whether you need to set up separate subdirectories\.