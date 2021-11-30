# Microsoft Smooth output group<a name="origin-server-mss"></a>

Follow this procedure if you have [determined](identify-downstream-system.md) that you will create a Microsoft Smooth output group\.

You and the operator of the downstream system must agree about the destination for the output of the Microsoft Smooth output group\. You will need this information when you [create the MediaLive channel](creating-smooth-output-group.md)\.

You must follow the procedure for each Microsoft Smooth output group\.

**To arrange setup of the destination**

1. Decide if you need two destinations for the output: 
   + You need two destinations for output from a [standard channel](plan-redundancy.md)\.
   + You need one destination for output from a single\-pipeline channel\.

1. Talk to the operator at the Microsoft IIS server to agree on a full path for the output\. Make a note of the URLs that you agree on\. For example:

   `https://203.0.113.55/sports/curling`

   `https://203.0.113.82/sports/curling`

1. Arrange with the operator to set up user credentials, if the protocol is HTTPS\. 

1. Find out if the downstream system has special connection requirements\. These connection fields are in the **General configuration** section for the Microsoft Smooth output group\. To display this page on the MediaLive console, in the **Create channel** page, in **Output groups** section, choose **Add**, then choose **Microsoft Smooth**\. Choose the group, then in **Microsoft Smooth settings**, open **General configuration**\.

1. Make a note of the information you have collected:
   + The URLs\.
   + The user name and password to access the Microsoft IIS servers, if the server requires authenticated requests\. Note that these user credentials relate to user authentication, not to the protocol\. User authentication is about whether the server will accept your request\. The protocol is about whether the request is sent over a secure connection\.
   + The settings for connection fields, if the downstream system has special requirements\.