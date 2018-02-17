# Deleting an Input Security Group<a name="delete-input-security-groups"></a>

Input security groups can be deleted but they cannot be edited\. 

**Important**  
If you delete an input security group that is associated with an input, the input becomes unusable because the input no longer has the required input security group\. Additionally, you can't attach another input security group to the input because you can't edit an input\. If the channel that is associated with that input is running, it continues to run and accept input according to the input security group rule that you deleted\. But if the channel is stopped \(manually or because of a problem\), the channel also becomes unusable\. 

We strongly recommend that you delete an input security group only if it's associated with an input that no longer exists\. 

To delete an input security group:

1. Open the AWS Elemental MediaLive console at https://console\.aws\.amazon\.com/medialive?region="region"\.

1. In the navigation pane, choose **Input security groups**\. 

1. On the **Input security groups** page, check the group or groups to delete\. 

1. Choose **Delete**\.