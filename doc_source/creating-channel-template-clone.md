# Creating a Channel from a Template or by Cloning<a name="creating-channel-template-clone"></a>

A channel contains the details that instruct AWS Elemental MediaLive how to transcode \(decode and encode\) and package your input into specific outputs\. 

To create a channel you must provide details about inputs, about one or more output groups and their destinations, about the outputs in each output group, and about the video, audio and caption encodes in each output\.

There are three ways to create a channel: 

+ **From scratch\.** The Create form contains some fields that display system defaults and contains other fields that are empty\. You can modify system defaults and complete empty fields as desired\. See [[ERROR] BAD/MISSING LINK TEXT](creating-channel-scratch.md)\.

+ **Using a built\-in template or custom template\.** See below\. 

+ **By cloning an existing channel\. **See below\. 

The following procedures assume that you are familiar with all the steps in creating a channel from scratch\. See [[ERROR] BAD/MISSING LINK TEXT](creating-channel-scratch.md)\.

## About Templates and Clones<a name="about-templates-and-clones"></a>

### About Built\-in Templates<a name="about-builtin-templates"></a>

AWS Elemental MediaLive includes built\-in templates\. Each template is displayed in the console list with a name and description\. Each template includes data for output groups and outputs, and most importantly, for encoding video to meet specific use cases \(as specified in the template description\)\. 

When you use a built\-in template, all sections of the **Create channel** page are populated with data except for the inputs and output destinations sections\. 

You can modify existing fields and complete empty fields as desired\.

### About Custom Templates<a name="about-custom-templates"></a>

You or another person in your organization may have created custom templates\. See [[ERROR] BAD/MISSING LINK TEXT](creating-custom-template.md)\. A template may contain nearly all the data required to create a complete channel, or it may contain only portions of the data\.

You need to obtain the templates you need and put them in a folder on the computer where you are working on the AWS Elemental MediaLive console\. This folder is the "custom template location"\. You perform this task in your computer's filesystem\. 

When you use a custom template, all sections of the **Create channel** page are populated with data from the JSON file, except for the input data: even if the template includes input data, that data will not be pulled into the **Create channel** page\. 

You can modify existing fields and complete empty fields as desired\.

### About Cloning<a name="about-cloning"></a>

Cloning lets you use an existing channel as the template for a new channel\. 

When you clone an existing channel, all sections of the **Create channel** page are populated with the data from the cloned channel, except for the input data, which is always left blank\. 

You can modify existing fields and complete empty fields as desired\.