# Settings for an RTMP Output<a name="output-settings-rtmp"></a>

In each **Output** page for an RTMP output group, you provide information about the packaging and delivery of the output, and about the video, audio, and captions encodes to create in the output\.

## RTMP Destination Section<a name="rtmp-destinations-section"></a>

For **RTMP destination A** and **RTMP destination B**, specify two destinations when the channel is set up as a [standard channel](channel-class.md), or one destination when it is set up as a single\-pipeline channel\. 

Complete each destination section as follows:
+ For **URL**, enter some of the information that you obtained when you [set up the downstream system](setting-up-downstream-system.md)\. Enter the URL in this format:

  `<protocol>://<IP address or domain>:<port>/<application name>`

  For example:

  **rtmp://203\.0\.113\.28:1935/live**
+ For **Stream**, enter the stream name \(also known as the *application instance* or *stream key*\)\. For example, **MyStream** or **03a38f838e0a**\.
+ If the server requires that you authenticate with a user name and password, complete the **Credentials** section\. Make sure that you have obtained the user name and password from the RTMP server and that you have already set up the user name and password in the Parameter Store\. For more information, see [Access to Amazon EC2 Systems Manager Parameter Store](https://docs.aws.amazon.com/medialive/latest/ug/about-EC2Password.html)\.

  Note that these credentials relate to user authentication, not to the protocol\. User authentication is about whether the RTMP server will accept your request\. The protocol is about whether the request is sent over a secure connection\.

## Output Settings Section<a name="rtmp-output-section"></a>
+ For **Connection retry interval** and **Num retries**, see [Reconnection Settings](#rtmp-connection-fields)\. 
+ If you want to connect to the destination over RTMPS, then for **Certificate Mode**, choose the option that is required by the RTMP server \(the downstream system\)\. If you connect over RTMP, the value in this field is ignored\.

### Reconnection Settings<a name="rtmp-connection-fields"></a>

There are several fields that control how MediaLive behaves if the connection to the RTMP server seems to drop:

**Cache length** \(on the output group page\) specifies how long to hold the output in memory, waiting for the RTMP server to respond\.

When that time expires, **Cache full behavior** \(on the output group page\) specifies whether to disconnect immediately or wait 5 minutes\.

If MediaLive disconnects, then **Restart delay** \(on the output group page\) specifies how long to wait before trying to reconnect\.

When MediaLive tries to reconnect, **Connection retry interval** \(on the output page\) specifies how often to retry\. **Num retries** \(on the output page\) specifies how many times to retry\. When the retries expire, this output stops\. The channel stops running only if all outputs lose their connections\.

## Stream Settings Section<a name="rtmp-output-section"></a>

In the **Stream settings** section, decide if you need to create more encodes for this output, based on the [workflow that you planned](planning-the-channel.md)\. By default, each output is set up with one video encode and one audio encode\. Choose the appropriate **Add** button or **Delete** button to set up the output with the encodes—video, audio, and captions—that you planned for this output\.

Typically, RTMP outputs contain one video asset, one or more audio assets, and zero or one captions assets\.

For information about the fields in each type of encode, see [Step 7: Set Up the Video Encode](creating-a-channel-step6.md), [Step 8: Set Up the Audio Encodes](creating-a-channel-step7.md), and [Step 9: Set up the Captions Encodes](creating-a-channel-step8.md)\. 