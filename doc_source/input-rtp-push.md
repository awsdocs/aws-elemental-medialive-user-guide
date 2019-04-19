# Channel Input—RTP Push Input<a name="input-rtp-push"></a>

Follow these guidelines to verify that the input is set up correctly\.

**To verify the setup of the input**

1. Look at the **Input destinations** section\. It shows the two locations on MediaLive that the upstream system will push the source to when the channel is running\. These locations were automatically generated when you created the input:
   + If the channel is set up as a standard channel, two locations are generated\. 
   + If the channel is set up as a single\-pipeline channel, one location is generated\. 

   For example, for an RTP Public input:

   **rtp://203\.59\.21\.50\.0:5000**

   **rtp://203\.59\.21\.131:5000**

   For example, for an RTP VPC input:

   **rtp://10\.99\.39\.87\.30\.100:5000**

   **rtp://192\.0\.2\.123:5000**

1. Look again at the **Input destinations** section\. 
   + If the section has an **Input security group** with a number beside it, then the input is an RTP Public input that has a MediaLive security group\. The input is correctly set up and you can continue\.
   + If the section has an **Input security group** without a number beside it, then the input is an RTP Public input that is missing a MediaLive input security group\. This input isn't correctly set up\. Typically, this situation occurs if, for example, you have input A attached to input security group B and then you delete B\. Input A is no longer useable\. You must recreate the input and attach an input security group to it before you can associate it with a channel that you are creating\. 
   + If the section doesn't have an **Input security group**, then the input is an RTP VPC input\. The input is correctly set up and you can continue\.