# Fields for the RTMP connection<a name="rtmp-connection"></a>

The following fields configure the logic for reconnection attempts:
+ **RTMP settings** – **Authentication scheme**
+ **RTMP settings** – **Additional settings** – **Cache length**
+ **RTMP settings** – **Additional settings** – **Restart delay**
+ **RTMP settings** – **Additional settings** – **Cache full behavior**
+ **RTMP outputs** – **Output settings** – **Connection retry interval**
+ **RTMP outputs** – **Output settings** – **Num retries**
+ **RTMP outputs** – **Output settings** – **Additional settings** – **Certificate mode**

**To configure a secure \(RTMPS\) connection to the destination**

1. **Authentication Scheme** – Specify the type of scheme\. Typically, choose **Common**\. Choose **Akamai** only if instructed to do so by the downstream system\. 

1. For **Certificate mode**, choose the option that is required by the downstream system\. 

   If you connect over RTMP, MediaLive ignores both these fields\.

**To configure for reconnection**
+ There are several fields that control how MediaLive behaves if the connection to the RTMP server seems to drop:
  + **Cache length** specifies how long to hold the output in memory, waiting for the RTMP server to respond\.
  + When that time expires, **Cache full behavior** specifies whether to disconnect immediately or wait 5 minutes\.
  + If MediaLive disconnects, then **Restart delay** specifies how long to wait before trying to reconnect\.
  + When MediaLive tries to reconnect, **Connection retry interval** specifies how often to retry\. **Num retries** specifies how many times to retry\. When the retries expire, this output stops\. The channel stops because the single output has lost its connection\.