# Setting Up the Downstream System for a Microsoft Smooth Output<a name="downstream-system-smooth"></a>

The downstream system is always a CDN that uses HTTP \(or HTTPS\) `PUT`\. Typically, the downstream system is a Microsoft IIS server\.

Set up the CDN so that the CDN expects MediaLive output at two inputs, one for each MediaLive channel pipeline\. Make a note of the input addresses, and of the input user name and input password, if applicable\. 