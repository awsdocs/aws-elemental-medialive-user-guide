# Creating a partner CDI push input in Amazon VPC<a name="input-create-cdi-partners"></a>

A partner CDI input is a specific configuration of a [CDI input](input-create-cdi-push.md)\. If you want to support automatic input failover for the CDI source attached to the channel, you must set up the two CDI inputs as *partners*\. For more information about partner CDI inputs, see [Partner CDI inputs](feature-cdi-partner.md)\.

The two inputs always work together, as the two inputs in an automatic failover pair\. The two inputs can be used only together, as a failover pair\.

You create a set of partner CDI inputs in two steps:
+ Create the first partner CDI input in the usual way\.
+ Then, create the second partner input from the first input\.

**To create the first partner CDI input**
+ If you already have a regular CDI input, you can use it as the first partner\. Skip this step and go to the step for creating the second partner, below\.

  If not, [create the input in the usual way](input-create-cdi-push.md)\. 

MediaLive creates the input and automatically creates two endpoints on that input\. These endpoints each have a private IP address from the subnet range, and they specify port 5000\. For example: 

`10.99.39.23:5000`

`192.0.2.54:5000`

Don’t provide this information to the upstream system until you have created the second partner\.

**To create the second partner CDI input**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the list of inputs, choose the first partner input\. The details for the input appear\.

   In the **Endpoints** section, you can see the endpoints that apply to this input\. For example: 

   `10.99.39.23:5000`

   `192.0.2.54:5000`

1. At the top of the page, choose **Create partner input**\. 

1. On the confirmation dialog, optionally choose to copy the tags, if any, from the first input\. 

1. Choose **Confirm**\.

   The **Input details** page for this input appears, showing information about the new input\.
   + In **Details**, the **Name** shows that the input has the same name as the first input, with the suffix "\- partner"\.
   + In **Details**, the partner **CDI ID **field shows the ID of the first input\. 
   + In **Endpoints**, the endpoints for the input are identical to the two endpoints for the first input, except that the port numbers are different\. For example:

     `10.99.39.23:5001`

     `192.0.2.54:5001`