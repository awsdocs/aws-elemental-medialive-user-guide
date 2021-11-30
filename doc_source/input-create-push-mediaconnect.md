# Creating a MediaConnect push input<a name="input-create-push-mediaconnect"></a>

Create your input before you create the channel that ingests the input\. 

You can set up a MediaConnect source as a single\-class or a standard\-class input\. You should have already read [Implementing pipeline redundancy](plan-redundancy-mode.md), to decide the class of channel and class of input you want\.

**To create an input in MediaLive**

1. You should have already worked with the MediaConnect user to request that they [set up flows for your content](emx-upstream.md)\. Make sure that the MediaConnect user gives you the following information: 
   + The ARN or ARNS for the flows\. Make sure that you know which flow is the "first flow" \(flow A\) and which is the "second flow" \(flow B\)\. For example:

     `arn:aws:mediaconnect:us-west-1:111122223333:flow:1bgf67:sports_event_A`

     `arn:aws:mediaconnect:us-west-1:111122223333:flow:9pmlk76:sports_event_B`

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. Complete the **Input details** section:
   + **Input** name – enter a name\.
   + **Input type** – choose **MediaConnect**\. 

1. Complete the **MediaConnect flows** section:
   + **Channel and input class** – choose the class for this input:
     + STANDARD\_INPUT
     + SINGLE\_INPUT 
   + **ARN for flow A** – specify the ARN for the flow that you identified as the first flow\. 

     If you created a second flow, then for **ARN for flow B**, specify the ARN for the second flow\. 

1. Complete the **Role ARN** section to choose a role for MediaLive to use with this input\. For information, see [IAM role and ARN](#mediaconnect-push-role-and-remember-arn)\. 

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and automatically creates two endpoints on that input\. MediaLive always creates two endpoints, even if you specified only one flow \(flow A\) for the input\.

1. At the same time, MediaLive automatically connects to the MediaConnect flows\.
   + If you specified two flows for the input, MediaLive instructs AWS Elemental MediaConnect to create two outputs and attach them to the two flows that you created in the first stage\.
   + If you specified only one flow for the input \(to support a single\-pipeline channel\), MediaLive instructs AWS Elemental MediaConnect to create one output and to attach it to the single flow that you created in the first stage\.

   If MediaConnect has two flows for the channel, it runs the flows in different Availability Zones—one zone for flow A, another zone for flow B\. Similarly, MediaLive runs each pipeline in a different Availability Zone—one zone for pipeline A, another zone for pipeline B\. 

   MediaLive coordinates with AWS Elemental MediaConnect to ensure that MediaLive runs the channel pipelines in the same two Availability Zones as AWS Elemental MediaConnect\. This setup ensures maximum resiliency if one flow fails\.

**Result of these procedures**  
As a result of this setup, one or two MediaConnect flows exist\. Each flow has a source that the upstream system is pushing to\. Each flow also has one output for the use of MediaLive\. The MediaConnect input specifies the ARNs for those outputs\. 

For a description of this setup that includes a diagram, see [Result of this procedure](emx-upstream.md#setup-result-emx) in the section about setting up a MediaConnect source\.

## IAM role and ARN<a name="mediaconnect-push-role-and-remember-arn"></a>

This section describes how to complete the **Role ARN** section on the **Create input** pane of the MediaLive console\.

You must choose a role for MediaLive to assume when it creates any input\. The role ensures that MediaLive succeeds in its request to MediaConnect to create outputs on the flows\. MediaLive sends this request as soon as you choose **Create** for this input\. 

**Note**  
This section on the MediaLive console is identical to the **IAM role** section on the **Create channel** page \(also on the MediaLive console\)\. The difference in the two usages is that on the **Create input** page, you are attaching the role to the input\. On the **Create channel** page, you are attaching the role to the channel\. You can use the same role \(for example, the **MediaLiveAccessRole**\) in both usages\.

There are two general scenarios for choosing a role, depending on whether your organization has a designated administrator\.

### Your organization has a designated administrator<a name="role-scenario-1"></a>

Your organization might have an administrator who manages this service\. That administrator has likely set up one or more roles: 
+ Ask the administrator or your manager which role to use\. Or if only one role is listed in **Use existing role**, choose that role\. 
+ If the only role that is listed is **MediaLiveAccessRole**, choose that role\. In addition, if the **Update** button is displayed beside this role name, choose the button\. \(The button does not always appear, but whenever it does appear, choose it to refresh the role\.\)
+ If you want the selected role to appear first in the list next time, select **Remember ARN**\. 

### Your organization has no administrator<a name="role-scenario-2"></a>

Your organization might not have a designated service administrator\. In this case, if none of your colleagues have set up a suitable role, you might have to create one yourself and then choose it\. 
+ You can create the default role, called **MediaLiveAccessRole**\. To first check if someone else has already created this role \(only one person needs to create it for all users in your AWS account\), look at **Create role from template**:
  + If this option is grayed out, this task has been done\. In that case, choose Use existing role, and then choose **MediaLiveAccessRole** from the list\. 
  + If this option is not grayed out, choose **Create role from template**, and then choose **Create IAM role**\. Next, choose that role from the list\. If MediaLive does not let you create the role, speak to an AWS IAM administrator in your organization about your permissions\. 
+ If the **MediaLiveAccessRole** has already been created and the **Update** button is displayed beside it, choose the button\. \(The button does not always appear, but whenever it does appear, choose it to refresh the role\.\)
+ If you want the selected role to appear first in the list next time, select **Remember ARN**\.