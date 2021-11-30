# Creating a channel from scratch<a name="creating-channel-scratch"></a>

A channel contains the details that instruct AWS Elemental MediaLive about how to transcode \(decode and encode\) and package your input into specific outputs\.

Before you start the process of creating a channel, you should [plan your upstream and downstream systems](container-planning-workflow.md) and [plan your channel](planning-the-channel-in-workflow.md) to identify the following elements:
+ Inputs that the channel will use
+ Output groups for the channel
+ Outputs \(within each output group\)
+ Video, audio, and captions encodes \(in each output\) that the channel will produce

There are three ways to create a channel: 
+ **Create from scratch\.** See the topics \(steps 1\-9\) in this chapter\.
+ **Use a built\-in or custom template\.** See [Creating a channel from a template or by cloning](creating-channel-template-clone.md)\.
+ **Clone an existing channel\.** See [Creating a channel from a template or by cloning](creating-channel-template-clone.md)\. 

**Note**  
For information about additional steps for setting up a channel for use in a multiplex program, see [Step 5: Create the channels](setting-up-multiplex.md#create-multiplex-channels-step)\.

**Topics**
+ [Getting ready](creating-a-channel-getready.md)
+ [Step 1: Complete the channel details](creating-a-channel-step1.md)
+ [Step 2: Attach inputs to the channel](creating-a-channel-step2.md)
+ [Step 3: Complete the settings for each input](creating-a-channel-step2a.md)
+ [Step 4: Complete the general settings](creating-a-channel-step3.md)
+ [Step 5: Create output groups and outputs](creating-a-channel-step4.md)
+ [Step 6: Set up the video encode](creating-a-channel-step6.md)
+ [Step 7: Set up the audio encodes](creating-a-channel-step7.md)
+ [Step 8: Set up the captions encodes](creating-a-channel-step8.md)
+ [Step 9: Save the channel](creating-a-channel-step9.md)