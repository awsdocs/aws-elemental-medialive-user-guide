# Step 1: Get Started<a name="creating-a-channel-step1"></a>

The first step to creating a channel is to select the role that AWS Elemental MediaLive will use with this channel\.

1. Before creating a channel, make sure you have created the input [[ERROR] BAD/MISSING LINK TEXT](creating-input.md) that you will attach to the channel\.

1. On the console, choose **Channels **in the navigation pane\.

1. In the content pane, choose **Create Channel**\. The **Create channel** page appears\.

1. Complete the fields in the **Channel and input details **pane, see below for details on specific fields\.

1. When ready, go to the next step\.

**IAM Role and Remember ARN**

You must choose a role for AWS Elemental MediaLive to assume, when it is working with this channel\. If you do not choose a role, you will not be able to create the channel\. Here are some tips for choosing the role:

+ If your organization has an administrator whose job is to manage this service, that administrator has likely set up one or more roles\. Ask the administrator or your manager which role to use\. Or if only one rule is listed in **Use existing role**, choose that role\. 

+ If your organization does not have a service administrator, you may have to create a role yourself and then choose it\. You can create and choose the default role, called MediaLiveAccessRole\. To first check if someone else has already created this role \(only one person needs to create it for all users in your AWS account\), look at **Create role from template**\. 

  + If this option is grayed out, this task has been done\. In this case, choose **Use existing role **and then select MediaLiveAccessRole from the list\. 

  + If this option is not grayed out, choose **Create role from template** and choose **Create IAM role**\. Then choose that role from the list\. If AWS Elemental MediaLive does not let you create the role, speak to an AWS IAM administrator about your permissions\. 

+ Check **Remember ARN** if you want the selected ARN to appear first in the list the next time you create a channel\.

For details about ARNs and the MediaLiveAccessRole role, see [[ERROR] BAD/MISSING LINK TEXT](trusted-entity-role.md)\.