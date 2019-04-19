# Creating a MediaConnect Push Input<a name="input-push-mediaconnect"></a>

There are three stages to creating a MediaConnect input in AWS Elemental MediaLive\. First, you set up flows in AWS Elemental MediaConnect, then you create an input in MediaLive, then you verify that the output has been automatically created in AWS Elemental MediaConnect\. 

**To create flows in AWS Elemental MediaConnect**

1. Follow the procedure in [Creating a Flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-create.html) in the *AWS Elemental MediaConnect User Guide* to create one or two MediaConnect flows: 
   + If the channel for this input will be set up as a [standard channel](plan-redundancy-mode.md), create two flows\.
   + If the channel for this input will be set up as a single\-pipeline channel, create one flow\.

   Complete the fields as follows: 
   + For **Name**, enter a name that includes A \(for the first flow\) and B \(for the second flow\)\. For example, **sports\_event\_A** and **sports\_event\_B**\. Using these letters will help you match the flows to the input pipelines in AWS Elemental MediaConnect\.
   + For **Availability Zone**, choose a different Availability Zone for each flow\. \(If you choose the same Availability Zone for both flows, MediaLive doesn't allow you to create the input\.\)
   + For the **Source **section, keep in mind that the source here is the source into AWS Elemental MediaConnect\. It has nothing to do with MediaLive\.
   + Don't create outputs or entitlements\. In the next stage, MediaLive will automatically create outputs\.
   + When you create the flow, AWS Elemental MediaConnect creates an ARN for each flow\. For example:

     **arn:aws:mediaconnect:us\-west\-1:111122223333:flow:1bgf67:sports\_event\_A** and

     **arn:aws:mediaconnect:us\-west\-1:111122223333:flow:9pmlk76:sports\_event\_B**

     Note that the ARNs include the flow names as the last portion\. 

1. Make a note of the ARN or ARNs\. You need them to set up the MediaLive input\.

**To create an input in MediaLive**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, enter a name\.

1. For **Input type**, choose **MediaConnect**\. 

1. In the **MediaConnect** section, for **ARN for flow A**, specify the ARN for the flow that you identified as flow A\. 

   If you created a second flow, then for **ARN for flow B**, specify the ARN for flow B\. 

1. Complete the **Role ARN** section to choose a role for MediaLive to use with this input\. For information, see [IAM Role and ARN](#mediaconnect-push-role-and-remember-arn)\. 

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and automatically creates two endpoints on that input\. MediaLive always creates two endpoints, even if you specified only one flow \(flow A\) for the input\.

1. At the same time, MediaLive automatically connects to the AWS Elemental MediaConnect flows\.
   + If you specified two flows for the input, MediaLive instructs AWS Elemental MediaConnect to create two outputs and attach them to the two flows that you created in the first stage\.
   + If you specified only one flow for the input \(to support a single\-pipeline channel\), MediaLive instructs AWS Elemental MediaConnect to create one output and to attach it to the single flow that you created in the first stage\.

   If AWS Elemental MediaConnect has two flows for the channel, it runs the flows in different Availability Zones—one zone for flow A, another zone for flow B\. Similarly, MediaLive runs each pipeline in a different Availability Zone—one zone for pipeline A, another zone for pipeline B\. MediaLive and AWS Elemental MediaConnect coordinate so that both services choose the same Availability Zone for flow and pipeline A and for flow and pipeline B\. This setup ensures maximum redundancy if one flow fails\.

**To verify the output in AWS Elemental MediaConnect**

1. To view the list of outputs for the flow or flows that you created, follow the procedure in [Viewing a List of Outputs of a Flow](docs.aws.amazon.com/mediaconnect/latest/ug/outputs-view-list.html) in the *AWS Elemental MediaConnect User Guide*\. 

   When you created the input in MediaLive, AWS Elemental MediaConnect automatically created outputs\. Therefore, you end up with the following:

   Flow A \(in MediaConnect\) – output for flow A \(in MediaConnect\) – source for A \(in MediaLive\)

   Flow B \(in MediaConnect\) – output for flow B \(in MediaConnect\) – source for B \(in MediaLive\) 

1. If you created two flows, make sure that there is one output for flow A and one output for flow B\. 

   Each output is assigned a name that consists of *MediaLive dash random characters*\. For example:

   **MediaLive\-ace74fa23**

## IAM Role and ARN<a name="mediaconnect-push-role-and-remember-arn"></a>

This section describes how to complete the **Role ARN** section on the **Create input** pane of the MediaLive console\.

You must choose a role for MediaLive to assume when it creates any input\. The role ensures that MediaLive succeeds in its request to AWS Elemental MediaConnect to create outputs on the flows\. MediaLive sends this request as soon as you choose **Create** for this input\. 

**Note**  
This section on the MediaLive console is identical to the **IAM role** section on the **Create channel** page \(also on the MediaLive console\)\. The difference in the two usages is that on the **Create input** page, you are attaching the role to the input\. On the **Create channel** page, you are attaching the role to the channel\. You can use the same role \(for example, the **MediaLiveAccessRole**\) in both usages\.

There are two general scenarios for choosing a role, depending on whether your organization has a designated administrator\.

### Your Organization Has a Designated Administrator<a name="role-scenario-1"></a>

Your organization might have an administrator who manages this service\. That administrator has likely set up one or more roles: 
+ Ask the administrator or your manager which role to use\. Or if only one role is listed in **Use existing role**, choose that role\. 
+ If the only role that is listed is **MediaLiveAccessRole**, choose that role\. In addition, if the **Update** button is displayed beside this role name, choose the button\. \(The button does not always appear, but whenever it does appear, choose it to refresh the role\.\)
+ If you want the selected role to appear first in the list next time, select **Remember ARN**\. 

### Your Organization Has No Administrator<a name="role-scenario-2"></a>

Your organization might not have a designated service administrator\. In this case, if none of your colleagues have set up a suitable role, you might have to create one yourself and then choose it\. 
+ You can create the default role, called **MediaLiveAccessRole**\. To first check if someone else has already created this role \(only one person needs to create it for all users in your AWS account\), look at **Create role from template**:
  + If this option is grayed out, this task has been done\. In that case, choose Use existing role, and then choose **MediaLiveAccessRole** from the list\. 
  + If this option is not grayed out, choose **Create role from template**, and then choose **Create IAM role**\. Next, choose that role from the list\. If MediaLive does not let you create the role, speak to an AWS IAM administrator in your organization about your permissions\. 
+ If the **MediaLiveAccessRole** has already been created and the **Update** button is displayed beside it, choose the button\. \(The button does not always appear, but whenever it does appear, choose it to refresh the role\.\)
+ If you want the selected role to appear first in the list next time, select **Remember ARN**\.