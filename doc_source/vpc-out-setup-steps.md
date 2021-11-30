# Setting up for VPC delivery<a name="vpc-out-setup-steps"></a>

**Note**  
The information in this section assumes that you are familiar with the general steps for [creating a channel](creating-channel-scratch.md)\. It also assumes that you have read [Preparing the upstream and downstream systems in the MediaLive workflow](container-planning-workflow.md) and have planned the workflow for your channel\.

**To set up for VPC delivery**

Follow these steps at some point when you are creating the channel\.

1. On the **Create channel** page, choose **Channel and input details** in the navigation pane\.

1. Complete the **Output delivery** section:
   + **Delivery method** – Choose **VPC**\.
   + **VPC settings** – Choose **Select subnets and security groups**\. 
   + **Subnets** – Choose one of the subnets that you obtained\. The dropdown list shows subnets in all VPCs, identified as follows:

     `<subnet ID> <Availability Zone of subnet> <IPv4 CIDR block of subnet> <VPC ID> <Subnet tag called "Name", if it exists>`

     For example:

     **subnet\-1122aabb us\-west\-2a 10\.1\.128\.0/24 vpc\-3f139646 Subnet for VPC endpoints**

     If the list of subnets is empty, choose **Specify custom VPC**, and enter the subnet ID in the field\. \(You need to enter only the subnet ID, for example, **subnet\-1122aabb**\.\) 

     MediaLive associates this subnet with pipeline 0\.
   + If your channel is a standard channel, add another subnet\. Still in **Subnets**, choose the second subnet\. This second time, the dropdown list shows only the subnets in the same VPC as the first subnet\.

     MediaLive associates this subnet with pipeline 1\.
   + **Security groups** – Choose the security group or groups that you obtained, following the same process as for the subnets\. The dropdown list shows security groups belonging to the VPC that you chose, identified as follows:

     `<security group ID> <description attached to this security group> <VPC ID>`
   + **EIPs for endpoints** – If applicable, enter the Elastic IP addresses that you obtained\. MediaLive takes the first Elastic IP address that you specify and associates it with pipeline 0\. It associates the second Elastic IP address \(if applicable\) with pipeline 1\.

1. Follow these guidelines when you create the output groups in the channel:
   + For the channel output groups that have destinations in your VPC or on Amazon S3, obtain the URL or bucket path\. You don't have to modify the destination syntax\. If the Amazon VPC user has set up the routing correctly, the outputs will successfully find these outputs in the VPC\.
   + For the channel output groups that have destinations that are not in your VPC, follow the usual procedure\. You don't have to modify the destination syntax\. If the Amazon VPC user has set up the routing correctly, the outputs will successfully find the outputs that are outside the VPC\. 

**Result**

When you set up for delivery via your VPC, MediaLive creates one or two elastic network interfaces in your VPC\. It creates one elastic network interface for a single\-pipeline channel, and two for a standard channel\.

If you choose to use Elastic IP addresses, MediaLive also associates those Elastic IP addresses with the elastic network interface\.

You can view the setup of the delivery point in the [details for the channel](monitoring-console.md)\. 