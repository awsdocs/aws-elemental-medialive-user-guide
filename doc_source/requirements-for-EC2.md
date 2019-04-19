# Requirements for AWS Systems Manager—Creating Password Parameters in Parameter Store<a name="requirements-for-EC2"></a>

The AWS Elemental MediaLive console includes a feature that lets a user create a password parameter in the AWS Systems Manager Parameter Store\. This feature is part of the **Create Channel** page\. This feature does not exist in the AWS CLI or REST API\.

You must decide if you want to give some or all of your users permission to use this feature\. \(If you don't give this access to any users, then an administrator must be responsible for creating parameters\.\)

## About the Feature for Creating Password Parameters<a name="about-EC2Password"></a>

The AWS Systems Manager Parameter Store is used extensively in AWS Elemental MediaLive\. It is likely that you will use this store\. The store holds passwords that MediaLive needs to retrieve and store files externally\. 

Here are some of the MediaLive functions that use this store to hold passwords:
+ An input of type RTMP Pull or type HLS Pull, if the connection is secure\. 
+ Fields in the channel that hold the URL to an external file, if the connection is secure\. An example of this type of field is **Avail blanking image**\.
+ The destination in an HLS output group or a Microsoft Smooth output group, if the connection is secure\.

In all these cases, MediaLive needs the user name and the password\. The password is always stored in a parameter\. Therefore, the console includes a **Username** field and a **Password parameter** field\. For an example of the relevant fields, open the MediaLive console, choose **Create channel**, **General settings**, **Avail blanking**, **Avail blanking image**, and then choose **Credentials**\.

## How Password Parameters Work<a name="how-passwordparam-works"></a>

The password parameter feature ensures that when the user is creating a channel, AWS Elemental MediaLive does not store passwords in plaintext\. It works as follows:
+ First, a user or administrator creates a password parameter in AWS Systems Manager Parameter Store\. The parameter is a name\-value pair where the name is something like **corporateStorageImagesPassword** and the value is the actual password\. 
+ Second, when a user is creating a channel or input in MediaLive and needs to enter a password, the user specifies the password parameter name instead of the password\. That name is stored in MediaLive\. The actual password is never stored in MediaLive\.
+ Finally, when the channel is running and MediaLive needs the password \(to either read or write to the external location\), it sends the password parameter name to Parameter Store and gets back the actual password in response\.

## Create Feature That Is Built into AWS Elemental MediaLive<a name="passwordparam-in-medialive"></a>

When a password field appears on the console, AWS Elemental MediaLive includes a feature that lets the user do one of the following:
+ Enter the name of an existing password parameter\.
+ Create a password parameter by entering the name\-value pair \(a parameter name and an actual password\)\. 

## Required Permissions<a name="passwordparam-permissions"></a>

Users must enter the name of a password parameter or select a name from the dropdown list\. Some users might need permission to create a password parameter within AWS Elemental MediaLive\.

### Permission to Enter a Name<a name="passwordparam-permissions-list"></a>

No special permission is required to enter the name of an existing password parameter on the AWS Elemental MediaLive console\. 

### Permission to Select a Name<a name="passwordparam-permissions-select"></a>

For the user to select a name from the dropdown list, the user must have permission for `GetParameters` in AWS Systems Manager\.

### Permission to Create<a name="passwordparam-permissions-create"></a>

For any user to create a password parameter on the AWS Elemental MediaLive console, that user must have permission to specific operations in AWS Systems Manager Parameter Store\. \(With this permission, the user can also create these password parameters ahead of time on the AWS Systems Manager console\. The user can choose the option that they prefer\.\)

You can give access to some or all users to create these password parameters\. Typically, you give this access only to users who are trusted with sensitive passwords; these might be users whom you have identified as advanced users:
+ If you give access only to advanced users, those users must be responsible for creating parameters at startup for the applicable assets and whenever a new asset is required by MediaLive\. The users can perform the setup on the MediaLive console or on the AWS Systems Manager console\.
+ If you don't give this access to any users, an administrator must be responsible for creating parameters at startup for the applicable assets and whenever a new asset is required by MediaLive\. An administrator might prefer to perform this setup on the AWS Systems Manager console\. 

### Permission to Modify and Delete<a name="passwordparam-permissions-delete-modify"></a>

If you want users to be able to modify and delete password parameters \(as well as create them\), give access to modify and delete operations\. The users will be able to modify and delete from the AWS Systems Manager Parameter Store\. \(There is no feature on the AWS Elemental MediaLive console for modifying and deleting\.\) 

You might choose to give this access to the users who have create permissions\. Or you might choose to give this access only to administrators\. 

The following table shows the actions in IAM that relate to access for the Parameter Store\.


| Permissions | Service Name in IAM | Actions | 
| --- | --- | --- | 
| Select | Systems Manager | GetParameters | 
| Create  | Systems Manager | PutParameter | 
| Modify and Delete  | Systems Manager | DeleteParameter`DeleteParameters``DescribeParameters``GetParameter``GetParameterHistory``GetParameters``GetParametersByPath` | 