# Editing an Input Security Group<a name="edit-input-security-group"></a>

You can edit any of the fields in an input security group\. You can perform these edits at any time, even if the input security group is attached to an input that is attached to a channel that is running\.

**To edit an input security group**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Input Security Groups**\.

1. On the **Input security groups** page, choose the input security group, and then choose **Edit**\.

1. Change any fields as appropriate, and then choose **Update**\.

   Wait for the input security **State** to return to **In use** or **Idle** before performing another action with this input security group\.

**To add, delete, or edit tags in an input security group**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Input Security Groups**\.

1. On the **Input security groups** page, choose the name of the input security group\. Do not choose **Edit**\.

1. On the **Input security group** page for this input security group, in the **Tags** section, add or delete tags\. To edit the value of an existing tag, delete the tag and add it again\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\.

   Wait for the input security **State** to return to **In use** or **Idle** before performing another action with this input security group\.