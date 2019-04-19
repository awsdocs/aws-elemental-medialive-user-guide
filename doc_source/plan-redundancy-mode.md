# Determining the Channel Class<a name="plan-redundancy-mode"></a>

AWS Elemental MediaLive supports two classes of channel—a standard channel and a single\-pipeline channel\. 

You set up each AWS Elemental MediaLive channel as one of these classes:
+ A standard channel has two processing pipelines, for redundancy 
+ A single\-pipeline channel has one pipeline\.

You must decide on the channel class now because the choice affects the setup you must perform on the upstream system and on the downstream system\.

**To decide on the channel class**

1. Contact the owner of the upstream system and the owner of the downstream system and find out what kind of redundancy they support\. The possibilities are the following\.
   + Both systems support only redundancy\. The upstream system always sends two source streams\. The downstream system always expects delivery at two destinations\. In this case, you must set up the channel as a standard channel\.
   + Both systems support only a single pipeline\. The upstream system can provide only one source stream\. The downstream system can handle delivery at only one destination\. In this case, you must set up the channel as a single\-pipeline channel\.
   + Both systems can support either one pipeline or two pipelines\. In this case, continue reading\.

1. If you can choose between a standard and single\-pipeline channel, then you should weigh the benefit of a standard channel \(support for high availability\) against the difference in processing charges for a standard channel compared to a single\-pipeline channel\. For information about charges for channels, see [https://aws.amazon.com/medialive/pricing/](https://aws.amazon.com/medialive/pricing/)\.

   We strongly recommend that you set up channels as standard channels\.
   + With two pipelines in the channel, if one of the pipelines fail, the other pipeline continues encoding and delivering output\. \(The failed pipeline automatically restarts within a few minutes\.\) The downstream system can be set up to detect failure of an output at one of its destinations and switch to using the output from the other destination\. 
   + With only one pipeline in the channel, there is no second pipeline to switch to if the first pipeline fails\. No output is will be delivered to the downstream system until the failed pipeline restarts itself\.

1. If you are sending output to AWS Elemental MediaPackage, you might want to implement input redundancy, which MediaPackage supports by default\. In this case, you should set up channels as standard channels\. In this way, MediaLive will send two identical outputs to the two inputs on the MediaPackage channel\. You will achieve redundancy in both MediaLive and MediaPackage\.

   If you don't want to implement input redundancy in MediaPackage, you might choose to set up a single\-pipeline channel\. There is no way to implement input redundancy in MediaPackage using a single\-pipeline MediaLive channel\.