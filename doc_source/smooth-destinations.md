# Fields for the output destination<a name="smooth-destinations"></a>

The following fields configure the destination of each Microsoft Smooth output\.
+ **Output group** – **Microsoft Smooth group destination** section
+ **Output group – Event configuration – Event ID mode** 
+ **Output group – Event configuration – Event ID**
+ **Microsoft Smooth settings** section – **General configuration** section:
  + **Connection retry interval** 
  + **Num retries**
  + **Filecache duration**
  + **Restart delay**
  + **Certificate mode**

## Complete the fields on the console<a name="smooth-specify-destination"></a>

The full path for each output in a Microsoft Smooth output group consists of the following:

`URL eventID streamInformation `
+ The URL and event ID are know as the *publishing points*\. For example:

  `https://203.0.113.18/sports/Events(1585232182)`
+ MediaLive generates the event ID using information that you provide\. For more information, expand **Event Configuration** on the console, and choose the **Info **link next to each field\.
+ MediaLive generates the stream ID\. It assigns a unique number to the stream, starting from 0\. For example: `/Streams(stream0)`\.

  You will be able to see the stream information when you look at the MediaLive logs for the output\.

**To specify the path and connection to the downstream system**

1. When you [discussed your requirements](origin-server-s3.md) with the operator of the Microsoft Smooth downstream system, you should have obtained the following information:
   + The URL for the destination or destinations\. For example:

     `https://203.0.113.55/sports/curling`

     `https://203.0.113.82/sports/curling`
   + The user name and password to access the Microsoft IIS server, if the server requires authenticated requests\. 
   + The settings for connection fields, if the downstream system has special requirements\.

1. Complete the **URL** fields in the **Microsoft Smooth group destinations** section\. Specify two destinations if the channel is set up as a standard channel, or one destination if it is set up as a single\-pipeline channel\. Don't worry about the event ID\. You will specify that in another field\.

1. Complete the **Credentials** section, if the downstream system provided you with a user name and password\. For the password, enter the name of the password stored on the AWS Systems Manager Parameter Store\. Don't enter the password itself\. For more information, see [Requirements for AWS Systems Manager—creating password parameters in parameter store ](requirements-for-EC2.md)\. 

1. If you obtained values to configure the connection, enter those values in the **General configuration** section on the **Microsoft Smooth group** page\.

1. Set up the event ID in the following fields: 

   **Output group settings – Event configuration – Event ID Mode**

   **Output group settings – Event configuration – Event ID**

   You can set up the event ID in three ways:
   + With an event ID that you specify – Set **Event ID mode** to **USE\_CONFIGURED**\. Then specify the ID\. For example, **curling**\. The event ID will look like this: **/Events\(curling\)**
   + With a timestamp – Set **Event ID mode** to **USE\_TIMESTAMP**\. MediaLive generates a Unix timecode based on the time that you start the channel\. The event ID will look like this: **/Events\(1585232182\)**
   + With no event ID – set **Event ID mode** to **NO\_EVENT\_ID**\. We strongly recommend that you don't use this method\.