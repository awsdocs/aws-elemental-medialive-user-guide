# IAM Role and ARN<a name="role-and-remember-arn"></a>

This section describes how to complete the **IAM role** section in the **General info** section of the **Channel and input details** pane\.

You must choose a role for MediaLive to assume when it works with this channel\. If you don't choose a role, you can't create the channel\. There are two general scenarios, depending on whether your organization has a designated administrator\.

**Note**  
This section on the MediaLive console is identical to the **IAM role** section on the **Create input** page for a MediaConnect push input \(also on the MediaLive console\)\. The difference in the two usages is that on the **Create channel** page, you attach the role to the channel\. On the **Create input** page, you attach the role to the MediaConnect input\. You can use the same role \(for example, the **MediaLiveAccessRole**\) in both usages\.

There are two general scenarios for choosing a role, depending on whether your organization has a designated administrator\.

## Your Organization Has a Designated Administrator<a name="role-scenario-1"></a>

Your organization might have an administrator who manages this service\. That administrator has likely set up one or more roles: 
+ Ask the administrator or your manager which role to use\. Or if only one rule is listed in **Use existing role**, choose that role\. 
+ If the only rule that is listed is **MediaLiveAccessRole**, choose that role\. In addition, if the **Update** button is displayed beside this role name, choose the button\. \(The button does not always appear, but whenever it does appear, choose it to refresh the role\.\)
+ If you want the selected ARN to appear first in the list next time, select **Remember ARN**\. 

## Your Organization Has No Administrator<a name="role-scenario-2"></a>

Your organization might not have a designated service administrator\. In this case, if none of your colleagues have set up a suitable role, you might have to create one yourself and then choose it\. 
+ You can create the default role, called **MediaLiveAccessRole**\. To first check if someone else has already created this role \(only one person needs to create it for all users in your AWS account\), look at **Create role from template**:
  + If this option is grayed out, this task has been done\. In that case, choose **Use existing role**, and then choose **MediaLiveAccessRole** from the list\. 
  + If this option is not grayed out, choose **Create role from template**, and then choose **Create IAM role**\. Next, choose that role from the list\. If MediaLive does not let you create the role, speak to an AWS IAM administrator about your permissions\. 
+ If the **MediaLiveAccessRole** has already been created and the **Update** button is displayed beside it, choose the button\. \(The button does not always appear, but whenever it does appear, choose it to refresh the role\.\)
+ If you want the selected ARN to appear first in the list next time, select **Remember ARN**\.