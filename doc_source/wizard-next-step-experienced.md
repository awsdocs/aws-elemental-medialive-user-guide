# Next steps—experienced video users<a name="wizard-next-step-experienced"></a>

If you have experience with video streaming and with other AWS services, you might want to add more MediaLive resources and more resources from other AWS services to the workflow\. Following are some of the ways that you can revise the workflow\. 
+ You can work with each service, using the AWS console or an AWS SDK\. For example, you can use the MediaLive console to add more MediaLive inputs to the channel\. Or you can use the AWS CLI to create a MediaStore container and then create a new MediaLive output in your channel that uses that container as a destination\.
+ You can use AWS CloudFormation to revise the AWS CloudFormation stack, to include more resources for AWS CloudFormation to create\. For example, you could create and attach more MediaLive inputs\. Or you could add an AWS Lambda function to the workflow\. For more information, display the details page for the workflow in the MediaLive console, then choose the appropriate link\.
+ You can use the Media Services Application Mapper \(MSAM\) to monitor your resources\. For more information, display the details page for the workflow in the MediaLive console, then choose the appropriate link\.

If you created a workflow that involves MediaStore, MediaPackage, and CloudFront, you should read the user guides for those services, to better understand their roles, and for information on feature of those services that you could add\.

You should also read the information on pricing for MediaLive, and for other AWS services, so that you understand the AWS charges that your workflow incurs\. For information about MediaLive charges, see [Pricing](pricing.md)\.