# About the workflow wizard<a name="wizard-about"></a>

## Supported inputs<a name="wizard-inputs"></a>

To use the workflow wizard, you must ingest a single source from one of the following:
+ A flow in AWS Elemental MediaConnect\.
+ Content from an AWS Elemental Link hardware device\.
+ Content from a mobile phone or webcam\. The source is delivered using the RTMP protocol\.
+ An MP4 file stored on Amazon S3 or an HTTP server\.

## Supported outputs<a name="wizard-outputs"></a>

With the workflow wizard, you can extract one video asset and one audio asset from the source and convert it to one or more of the following types of output:
+ Output to send to an AWS Elemental MediaPackage channel, for delivery to Amazon CloudFront\. CloudFront distributes the content to your end users\.
+ Output to send to an AWS Elemental MediaStore container, for delivery to CloudFront\. CloudFront distributes the content to your end users\.
+ Output to Facebook, Twitch, or YouTube\.

## Low\-touch setup<a name="wizard-low-touch"></a>

The workflow wizard automatically performs as much setup as possible in the upstream system\. For example, your source might be in MediaConnect but you might not have created the flow\. In this case, the workflow wizard automatically creates the flow for you\.

The workflow wizard also automatically performs as much setup as possible in the downstream system or systems\. For example, you might be sending to MediaPackage, but you might not have created the MediaPackage channel and might not have set up CloudFront\. In this case, the workflow wizard performs the setup in those services\. 

The workflow wizard works best when you use it to create these resources, rather than using existing resources\. 