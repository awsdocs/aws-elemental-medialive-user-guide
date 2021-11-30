# Requirements for Amazon CloudFront<a name="requirements-for-CFront"></a>

MediaLive includes a workflow wizard\. One of the options in the wizard is to deliver output to AWS Elemental MediaPackage and from there to Amazon CloudFront\. Therefore, for users to create a workflow with delivery to MediaPackage, users need permissions in CloudFront\. 


| Permissions | Service name in IAM | Actions | 
| --- | --- | --- | 
| Use the workflow wizard to create the CloudFront distribution that is associated with a MediaPackage channel, if your organization supports MediaPackage as an output destination\.Use the workflow wizard to delete a workflow that includes a CloudFront distribution\. | CloudFront |  `ListDistributions`\\ `DescribeDistribution` `CreateDistribution` `DeleteDistribution`   | 

CloudFrontCreate and delete a CloudFront distribution, if your organization supports MediaPackage as an output destination\.

Note how the required permissions here are very different from the permissions because the workflow wizard actually creates the distribution\.