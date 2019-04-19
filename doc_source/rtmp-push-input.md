# Creating an RTMP Push Input<a name="rtmp-push-input"></a>

Create your input before you create the channel that ingests the input\. 

**To create an RTMP push input**

1. Obtain the ID of the [input security group](purpose-input-security-groups.md) that you will use with this input\. \(Or if you will create an input security group at the same time as you create this input, obtain the IP addresses for the input security group\.\) Obtain the [application name and application instance](planning-rtmp-push.md) that you identified when planning the workflow\. 

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, enter a name\.

1. For **Input type**, choose **RTMP \(push\)**\. 

1. In the **Network mode** section, choose **Public**\.

1. In the **Input security group** section, specify the group to attach to this push input\. You can choose an existing group, or you can create a group\. For more information about security groups, see [Working with Input Security Groups](working-with-input-security-groups.md)\. 

1. In the **Input destinations** section, for **Destination A**, enter the application name and application instance for one of the sources\. For example, `live` and `curling`\. The names that you enter must match the names that the upstream system assigned to the source\. If they do not, MediaLive might detect the source but does not process it\. 

1. In the **Input destinations** section, for **Destination B**, enter the application name and application instance for the other source\. \(If the channel is set up as a single\-pipeline channel, leave this destination empty\.\)

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and automatically creates two endpoints on that input\. The endpoints include the application name, the application instance, and the port 1935\. For example:

   `rtmp://203.59.21.13:1935/live/curling`

   `rtmp://59.21.13.191:1935/live/curling2`

   MediaLive always creates two endpoints:
   + If the channel for this input will be set up as a standard channel, both endpoints will be used\. 
   + If the channel for this input will be set up as a single\-pipeline channel, only the first endpoint will be used\. MediaLive won't expect to receive content at the second endpoint\. 

1. Provide the upstream system with the following information:
   + If the channel for this input will be set up as a standard channel, provide both locations\. The upstream system must push the video streams to these locations\.
   + If the channel for this input will be set up as a single\-pipeline channel, provide only the first location\. The upstream system must push its one stream to this location\.