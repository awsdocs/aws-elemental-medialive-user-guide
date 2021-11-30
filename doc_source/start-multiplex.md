# Starting the multiplex<a name="start-multiplex"></a>

To start streaming the MPTS, start the multiplex and the channels\. You can start the channels and then start the multiplex\. Or you can start the multiplex and then start the channels\. 

If any channels are multi\-input channels, the standard recommendations about starting and restarting these channels apply\. For more information, see [Starting and restarting a channel that has multiple inputs](ips-start-channel-multi-inputs.md)\.

**Contents of the MPTS**

After you start the multiplex and channels, MediaLive starts all these components\. MediaLive creates two multiplex pipelines, each of which creates a separate MPTS asset\. The MPTS contains the following: 
+ The SDT contains an entry for each program\.
+ The PAT contains an entry for each program that has a MediaLive channel associated with it\.
+ The PMT for each program contains an entry for each stream that is being used\. When you created the programs, MediaLive allocated the PIDs for all possible program streams\. At runtime, the PMT references only those PIDs that actually contain content\.
+ One PID for each stream\. 

If you add or remove programs and channels while the multiplex is running, or if you modify channels while the multiplex is running, MediaLive modifies the MPTS tables dynamically\.

**Encoding**

MediaLive encodes the content in each channel in the regular way, except that the MediaLive multiplex continually communicates with each MediaLive channel to provide a bitrate for each video segment\. The MediaLive multiplex creates an MPTS from the output of all the channels\.

**Distribution**

The MPTS is an RTP output\. MediaLive creates and delivers the MPTS to AWS Elemental MediaConnect in the account associated with the MediaLive that is creating the MPTS\. AWS Elemental MediaConnect automatically sets up the RTP output as an entitled source\. You don't have to perform any steps to set up this entitled source\. But in order to complete the distribution of the MPTS, you must create a flow that uses that entitled source\.

The entitlement name includes the string "multiplex" and the multiplex ID, so that MediaConnect users can easily identify it\. 

For more information about entitled sources, see [Creating a Flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-create.html) in the *AWS Elemental MediaConnect User Guide*\.