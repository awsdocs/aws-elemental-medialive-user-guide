# Pipeline locking<a name="pipeline-lock"></a>

Pipeline locking is a feature that controls some of the behavior of the [pipeline redundancy](plan-redundancy-mode.md) feature of MediaLive\. When you create a standard channel, in order to implement pipeline redundancy, the channel has two pipelines\. The pipeline locking feature ensures that the two outputs are frame\-accurate with each other\. You can configure the *mode* for pipeline locking\. You can't disable pipeline locking\.

**Topics**
+ [Requirements for pipeline locking](pipeline-locking-requirements.md)
+ [Step 1: Verifying the input](pipeline-locking-verify-input.md)
+ [Step 2: Setting up for pipeline locking](pipeline-locking-set-up.md)
+ [Troubleshooting](pipeline-locking-tshoot.md)