# Requirements for AWS Elemental MediaLive Features<a name="requirements-for-medialive"></a>

You must give your users access to AWS Elemental MediaLive features\. The permissions for MediaLive can be divided into three categories:
+ Permissions to create – Permissions to create, modify, and delete channels, inputs, input security groups, or reservations
+ Permissions to view – Permissions to view the details of channels, inputs, input security groups, and reservations
+ Permissions to run – Permissions to start and stop channels

You might choose to give different access to different kinds of users\. For example, you might decide that "basic operators" should not have create permissions\. 

In particular, you must decide whether to restrict the ability to work with reservations; you might decide to give this access only to administrators or advanced users\. For more information about reservations, see [Working with Reservations in AWS Elemental MediaLive](reservations.md)\.

The following table shows the operations in IAM that relate to access for MediaLive\.


| Permissions | Service Name in IAM | Actions | 
| --- | --- | --- | 
| Create, Modify, and Delete Channels, Inputs, and Input Security Groups | MediaLive | One or more write operations  | 
| View Channels, Inputs, and Input Security Groups | MediaLive | One or more list operationsOne or more read operations | 
| Run Channels | MediaLive | StartChannel`StopChannel` | 
| Attach Tags to Channels, Inputs, and Input Security Groups When Creating Those Resources | MediaLive | CreateTag`DeleteTags``ListTagsForResources` | 
| Create, Modify, Delete, and View Reservations and Offerings | MediaLive |  `DeleteReservation` `DescribeOffering` `DescribeReservation` `ListOfferings` `ListReservations` `PurchaseOffering`  | 