# HLS output group to MediaStore<a name="origin-server-ems"></a>

Follow this procedure if you [determined](identify-downstream-system.md) that you will create an HLS output group, with AWS Elemental MediaStore as the destination\. 

You and the operator of the downstream system must agree about the destination for the output of the HLS output group\. You will need this information when you [create the MediaLive channel](creating-hls-output-group.md)\.

You must follow the procedure for each HLS output group\.

**To arrange setup of the destination**

1. Decide if you need two destinations for the output: 
   + You need two destinations for output from a [standard channel](plan-redundancy.md)\.
   + You need one destination for output from a single\-pipeline channel\.

1. If you have two destinations, the destination paths must be different from each other in some way\. At least one of the portions of one path must be different from the other\. It is acceptable for all the portions to be different\. 

   You can design the full destination paths now, or you can decide only on the container name or names:
   + If you want to design the full paths now, but you aren't familiar with the destination requirements for an HLS output, see [Step 1: Design the path for the output destination](hls-destinations-design-step.md)\. You and the MediaStore user must agree on the containers that you want to use\.
   + If you want to decide only on the containers, you and the MediaStore user must agree on which containers to use\.

1. Ask the MediaStore user to create any containers that don't already exist\. 

1. Obtain the data endpoint for the container or containers\. For example: 

   `https://a23f.data.mediastore.us-west-2.amazonaws.com`

   `https://fe30.data.mediastore.us-west-2.amazonaws.com`

   You need the data endpoints\. You don't need the container name\.

Note that you don't need user credentials to send to MediaStore containers\. MediaLive has permission to write to the MediaStore container via the trusted entity\. Someone in your organization should have already set up these permissions\. For more information, see [Reference: summary of requirements for the MediaLive trusted entity](trusted-entity-requirements.md)\.