# Getting ready<a name="vpc-out-get-ready-subnets"></a>

An Amazon VPC user must set up the VPC and identify subnets and security groups for the channel\. 

**To set up the VPC**

1. Provide your Amazon VPC user with the following guidelines:
   + Guideline for the subnets and Availability Zones – See [Identifying subnet and Availability Zone requirements](vpc-out-AZ-subnet-reqs.md)
   + Guideline for the security group for channel endpoints subnets – The security group or groups must follow these rules: 
     + The combined rules of the security groups must allow outbound traffic from the endpoint to all the output destinations\. These destinations might be on your VPC, destinations on AWS services, and destinations on the public internet\.
   + Guideline for the security group for destination subnets – The security group or groups must follow these rules: 
     + The combined rules of the security groups must allow inbound traffic from the channel endpoints\. 

1. Determine if you need to identify EIPs to associate with the channel\. If the channel has output groups with destinations outside your VPC, you must provide a mechanism for the content to leave the VPC\. One way to do this is to associate EIPs with the channel endpoints\. These endpoints appear in the diagram in [How VPC delivery works](vpc-out-how-it-works.md) Speak to the Amazon VPC user about your requirements\. 

   If you decide to associate EIPs with the channel endpoints, identify those EIPs\. 

1. After the Amazon VPC user has performed the setup, obtain the following information:
   + The ID of the VPC or VPCs\.
   + The IDs of the subnets and Availability Zones for the channel endpoints\.
   + The IDs of the subnets and Availability Zones for the destinations\. 
   + The IDs of the security groups for the subnets\.
   + The elastic IP address to associate with the elastic network interfaces of the channel endpoints\.

1. Delivery via the VPC depends on appropriate setup for routing and DNS\. of the VPC network\. Provide the Amazon VPC user with these guidelines:
   + If you expect addresses with a domain name to reach the VPC, or if you expect the VPC to reach addresses with a domain name, you must set up a DNS to resolve those domain names\. This requirement applies equally to AWS services that might have domain names\.
   + If any communication with the public internet is expected, you will need either a NAT or an Internet Gateway in your VPC\.
   + Inside the VPC, you must configure routing tables, to allow communication between the subnets you intend to use\.
   + All IP addresses must be IPV4\.