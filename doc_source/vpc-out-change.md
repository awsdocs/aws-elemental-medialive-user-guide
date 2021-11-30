# Changing the setup<a name="vpc-out-change"></a>

If you have set up a channel for VPC delivery, note the following:
+ You can't change an existing channel to either start delivering via your VPC or stop delivering via your VPC\.
+ You can't change the [channel class](plan-redundancy-mode.md) on an existing channel that is set up for delivery via your VPC\.
+ If you add another input that uses your VPC, make sure that it follows the already [established rules](vpc-out-AZ-subnet-reqs.md) for VPCs, subnets, and Availability Zones\.
+ If you delete the channel or if you delete all the output groups, MediaLive deletes the elastic interface points that it created in your Amazon EC2 instance\.