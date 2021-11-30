# Step 2: Set up the downstream system<a name="getting-started-step2"></a>

In this tutorial, the downstream system \(the destination for the output from MediaLive\) is AWS Elemental MediaPackage\. 

You must set up a channel in AWS Elemental MediaPackage, and you must set it up now because you need the two input URLs that AWS Elemental MediaPackage generates\. You enter these input URLs into MediaLive\.

**To set up the downstream system**

1. Sign in to the AWS Management Console and open the MediaPackage console at [https://console\.aws\.amazon\.com/mediapackage/](https://console.aws.amazon.com/mediapackage/)\.

1. In a new web browser tab or window, display the [Getting Started for AWS Elemental MediaPackage](https://docs.aws.amazon.com/mediapackage/latest/ug/getting-started.html) and follow steps 1 to 3 to create one channel and its endpoint\.

1. Make a note of the data that AWS Elemental MediaPackage has generated: two input URLs and their associated names and passwords\. For example, the data for one input URL might be:
   + `https://39fuo4.mediapackage.us-east-1.amazonaws.com/in/v1/88dpie/channel`
   + `ue739wuty`
   + `due484u`

   Your channel might be in a different Region from the example\.

1. Keep the web browser open; don't close it yet\.