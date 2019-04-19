# Channel Input—RTMP Push Input<a name="input-rtmp-push"></a>

Follow these guidelines to verify that the input is set up correctly\.

**To verify the setup of the input**

1. Look at the **Input destinations** section\. It shows the two locations on MediaLive that the upstream system will push the source to when the channel is running\. These locations were automatically generated when you created the input: 
   + If the channel is set up as a standard channel, two locations are generated\. 
   + If the channel is set up as a single\-pipeline channel, one location is generated\. 

   Each location consists of an address portion that was automatically generated, appended by a folder that you specified when you created the input\. 

   For example, for an RTMP Public push input:

   **rtmp://203\.0\.113\.111:1935/movies/classic**

   **rtmp://203\.0\.113\.22:1935/movies/classic**

   For example, for an RTMP VPC push input:

   **rtmp://10\.99\.20\.40:1935**

   **rtmp://192\.0\.2\.131:1935**

1. Look again at the **Input destinations** section\. 
   + If the section has an **Input security group** with a number beside it, then the input is an RTMP Public input that has a MediaLive security group\. The input is correctly set up and you can continue\.
   + If the section has an **Input security group** without a number beside it, then the input is an RTMP Public input that is missing a MediaLive input security group\. This input isn't correctly set up\. Typically, this situation occurs if, for example, you have input A attached to input security group B and then you delete B\. Input A is no longer useable\. You must recreate the input and attach an input security group to it before you can associate it with a channel that you are creating\. 
   + If the section doesn't have an **Input security group**, then the input is an RTMP VPC push input\. The input is correctly set up and you can continue\.