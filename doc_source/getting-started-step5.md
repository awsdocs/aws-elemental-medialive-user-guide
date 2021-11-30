# Step 7: Create an HLS output group<a name="getting-started-step5"></a>

Once you have set up the input, you continue with the channel creation by creating an output group\. In this tutorial, you set up an HLS output group\.

**To create an output group**

1. On the **Create channel** page, in the **Output groups** section, choose **Add**\. 

1. In the **Add output group** section, choose **HLS**, and then choose **Confirm**\. 

1. In the **HLS group destination A** section, for **URL**, enter the first input URL that AWS Elemental MediaPackage created for you in [Step 2: Set up the downstream system](getting-started-step2.md)\. For example, **https://39fuo4\.mediapackage\.us\-east\-1\.amazonaws\.com/in/v1/88dpie/channel**``\. 

1. For **Credentials**:
   + For **Username**, enter the user name that corresponds to this URL\. For example, **ue739wuty**\. 
   + For **Password**, choose **Create parameter**\. For **Name**, enter **DestinationA\-MyHLS**\. For **Password**, enter the password that corresponds to the URL\. For example, **due484u**\.

1. Choose **Create parameter**\.

   You have created a parameter called **DestinationA\-MyHLS** that holds the password **due484u**\. The parameter is stored in the AWS Systems Manager Parameter Store\. For more information, see [About the feature for creating password parameters](requirements-for-EC2.md#about-EC2Password)\.

1. For **HLS group destination B**, for **URL**, enter the second input URL that AWS Elemental MediaPackage created for you in [Step 2: Set up the downstream system](getting-started-step2.md)\. For example, **https://mgu654\.mediapackage\.us\-east\-1\.amazonaws\.com/in/v1/xmm9s/channel**\. 

1. For **Credentials**:
   + For **Username**, enter the user name that corresponds to this URL\. For example, **883hdux**\. 
   + For **Password**, choose **Create parameter**\. For **Name**, enter **DestinationB\-MyHLS**\. For **Password**, enter the password that corresponds to the URL\. For example, **634hjik**\.

1. Choose **Create parameter**\.

   You have created a parameter called **DestinationB\-MyHLS** that holds the password **634hjik**\. The parameter is stored in the AWS Systems Manager Parameter Store\. 

1. In the **HLS settings** section, for **Name**, enter **MyHLS**\. 

1. For **CDN settings**, choose **Hls webdav**\. This is the connection that AWS Elemental MediaPackage \(the downstream system for the channel output\) uses\. 

   Leave the defaults for all the other **CDN settings** fields\.

1. For all other fields in this pane, keep the default values\.