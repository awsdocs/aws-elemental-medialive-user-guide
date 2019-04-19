# Setting Up the Downstream System for an RTMP or RTMPS Output<a name="downstream-system-rtmp"></a>

The downstream system is always a server that uses RTMP or RTMPS\. The server might be a CDN\.

Set up the RTMP server so that it expects MediaLive output at two inputs, one for each MediaLive channel pipeline\. 

Perform the necessary setup on the RTMP server to obtain the following information for each input:
+ URL for the output to send to\.
+ Port number\.
+ Application name\. \(The application name might be identical for both inputs\.\)
+ Stream name\.

Make a note of the URLs and port numbers\.

The URL might include a path portion in the format `<string>/<string>`\. In this case, the first string is the application name and the second string is the stream name\. In addition, the RTMP server might refer to the stream name as the application instance or the stream key\.