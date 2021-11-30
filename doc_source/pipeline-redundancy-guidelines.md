# Deciding whether to implement pipeline redundancy<a name="pipeline-redundancy-guidelines"></a>

To determine the channel class to implement, you must decide if you want to and are able to implement pipeline redundancy\.

## Step 1: Decide if you want to implement pipeline redundancy<a name="decide-class-step-want"></a>

Decide if you *want* to implement pipeline redundancy\. As well as the obvious benefit of redundant pipelines, consider the following points:\.
+ If you are sending output to AWS Elemental MediaPackage, you might want to implement pipeline redundancy in order to support *input redundancy* in MediaPackage\. MediaLive will send two identical outputs to the two inputs on the MediaPackage channel\. If there is a pipeline failure in MediaLive, MediaPackage has logic to seamlessly switch the input it uses\.
+ Weigh the benefit of a standard channel against the difference in processing charges for a standard channel compared to a single\-pipeline channel\. For information about charges for channels, see [https://aws.amazon.com/medialive/pricing/](https://aws.amazon.com/medialive/pricing/)\.
+ If you decide you don't yet want to implement pipeline redundancy, you can set up to leave open the option of implementing it later on\. The procedures later in this section explain how to set up in this way\.

## Step 2: Decide if you can implement pipeline redundancy<a name="decide-class-step-ability"></a>

If you decide that you want to set up a standard channel, you must determine if you *can *set up a standard channel\. Follow these steps:
+ Contact the upstream system to determine if they can send you two source streams for each input\. If they can't, then you can't set up as a standard channel\.

  In a multiple\-input channel, all the inputs must have two source streams\. If you have source content coming from several upstream systems, every upstream system must be capable of providing two sources\. If they can't all provide two sources, you can't set up as a standard channel\.
+ Contact the downstream system to determine if the downstream system can handle two sets of identical outputs from MediaLive and to switch as required\. Note that, as described earlier in this decision section, MediaPackage can always handle two outputs\.

  If the downstream system doesn't have this ability, there is no advantage to setting up as a standard channel\. 

## Step 3: Follow the correct procedure<a name="decide-class-step-procedure"></a>

After you have identified the pipeline redundancy option that you will implement in the channel, see the following sections for more information:
+ If you want to implement pipeline redundancy immediately, and the upstream system can provide two source streams, then see [Setting up a standard channel](standard-channel-procedure.md)\.
+ If you don't want to implement pipeline redundancy for now, but you want to allow for easy upgrade to pipeline redundancy later, then see [Setting up a single\-pipeline channel with upgrade options](single-channel-upgrade.md)\.
+ If you don't want to implement pipeline redundancy now or in the future, then see [Setting up a single\-pipeline channel without upgrade potential](single-pipeline-no-upgrade.md)\.