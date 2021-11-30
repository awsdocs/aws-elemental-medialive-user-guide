# Working with input security groups<a name="working-with-input-security-groups"></a>

An *input security group* contains a list of rules\. Each rule is a range of IP addresses \(CIDR blocks\) that are allowed to push content to MediaLive\. When you attach an input security group to an input, you apply a rule to that input—only an upstream system with an IP address from one of the ranges in that input security group is allowed to push content to that input\. MediaLive will ignore push requests from IP addresses not covered by that input security group\. 

You can include up to 10 rules \(IP address ranges or CIDR blocks\) in one input security group\.

You can attach the same input security group to any number of inputs\.

**Topics**
+ [Purpose of an input security group](purpose-input-security-groups.md)
+ [Creating an input security group](create-input-security-groups.md)
+ [Editing an input security group](edit-input-security-group.md)
+ [Deleting an input security group](delete-input-security-group.md)