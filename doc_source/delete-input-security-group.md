# Deleting an Input Security Group<a name="delete-input-security-group"></a>

 You can delete an input security group so long as it is not attached to any inputs\. 

**To delete an input security group**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Input security groups**\.

1. On the **Input security groups** page, look at the **State** for the group to delete: 
   + If the **State** is **Idle**, choose the group, and then choose **Delete**\. 
   + If the **State** is **In use**, continue with this procedure\. 

1. Make a note of the ID of the input security group\. For example, 1234567\.

1. Choose the group, and then choose **Edit**\. 

1. On the **Edit input security group** page, look at the **Inputs** on the right side and count how many inputs are attached to this input security group\.

1. Choose the first input\. Then on the page for that input, choose **Edit**\. On the **Edit** page, in the **Input security group**, either create a new input security group for this input or choose another group \(make sure you don't rechoose the same group; check the ID that you noted earlier\)\. Choose **Update** so that this input is no longer attached to the input security group that you want to delete\.

1. If there are still more inputs associated with this input group, then in the navigation pane, choose **Input security groups**, and repeat these steps to detach this input security group from all the inputs\. 

1. After detaching the last input from this input security group, wait for the **State** of the input security group to specify **Idle**\. Then choose the group, and choose **Delete**\. 

**Topics**