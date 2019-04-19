# Summary of Step 1 Access Requirements<a name="setup-users-step-1-summary"></a>

The following table shows all the types of permissions that you might need to assign to users\. 


| Feature | Corresponding Service in IAM | Tasks | Actions to Include in the Policy  | 
| --- | --- | --- | --- | 
| MediaLive Features | MediaLive | Create, modify, and delete channels, inputs, and input security groups | One or more List operationsOne or more Read operationsOne or more Write operations  | 
|  | MediaLive | View channels, inputs, and input security groups | One or more List operationsOne or more Read operations | 
|  | MediaLive | Run channels | StartChannel`StopChannel` | 
|  | MediaLive | Create, modify, delete, and view offerings and reservations |  `DeleteReservation` `DescribeOffering` `DescribeReservation` `ListOfferings` `ListReservations` `PurchaseOffering`  | 
|  | MediaLive | Attach tags when creating a resource | CreateTags`DeleteTags``ListTagsForResources` | 
| Monitoring Channel Health | CloudWatch |  |  `ListMetrics` `GetMetricData` `GetMetricStatistics`  | 
| Setting Up Events | CloudWatch Events |  | All actionsThe managed policy `CloudWatchEventsFullAccess` provides these permissions | 
| Setting Up Channel Logging | Amazon CloudWatch Logs | View logs | FilterLogEvents`GetLogEvents` | 
|  |  | Set retention policy | DeleteRetentionPolicy`PutRetentionPolicy` | 
| Creating a VPC input | EC2 | View the VPC subnets and VPC security groups on the MediaLive console  | DescribeSubnets`DescribeSecurityGroups` | 
| Simple Option for the Trusted Entity Role | IAM | Create the MediaLiveAccessRole |  `CreateRole` `PutRolePolicy` `AttachRolePolicy`  | 
|  |  | Choose the MediaLiveAccessRole |  `ListRole` `PassRole`   | 
|  |  | Update the MediaLiveAccessRole |  `GetRolePolicy` `PutRolePolicy` `AttachRolePolicy`  | 
| Setting Up Email Notification |  Amazon SNS  |  | All actionsThe managed policy `AmazonSNSFullAccess` provides these permissions | 
| AWS Systems Manager | Systems Manager | Create a password parameter using the MediaLive console or the AWS Systems Manager console |  `DeleteParameter` `DeleteParameters` `DescribeParameters` `GetParameter` `GetParameterHistory` `GetParameters` `GetParametersByPath` `PutParameter`  | 
|  | Systems Manager | Choose a password parameter from the dropdown list on the MediaLive console | DescribeParameters | 