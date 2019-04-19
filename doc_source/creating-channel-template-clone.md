# Creating a Channel from a Template or by Cloning<a name="creating-channel-template-clone"></a>

A channel contains the details that instruct AWS Elemental MediaLive how to transcode \(decode and encode\) and package your input into specific outputs\. 

To create a channel, you provide details about inputs, about one or more output groups and their destinations, about the outputs in each output group, and about the video, audio, and caption encodes in each output\.

There are three ways to create a channel: 
+ **From scratch\.** The **Create** form on the MediaLive console contains some fields that display system defaults and other fields that are empty\. You can create a channel from scratch by modifying the system defaults and by completing the appropriate empty fields\. For more information, see [Creating a Channel from Scratch](creating-channel-scratch.md)\.
+ **Using a built\-in template or custom template\.** You can use a template to create a channel, and reuse the template to create more channels\. For more information, see [Creating a Channel from a Template](creating-channel-template.md)\. 
+ **By cloning an existing channel\.** You can clone an existing channel, and then edit the settings for the new \(cloned\) channel\. For more information, see [Creating a Channel by Cloning](creating-channel-clone.md)\.

The procedures in the following topics show how to create a channel by using a template or by cloning\. Before you use the procedures, you should understand how to create a channel from scratch\. For more information, see [Creating a Channel from Scratch](creating-channel-scratch.md)\.

**Topics**
+ [About Templates](#about-templates)
+ [About Cloning](#about-cloning)
+ [Creating a Channel from a Template](creating-channel-template.md)
+ [Creating a Channel by Cloning](creating-channel-clone.md)
+ [Creating a Custom Template](creating-custom-template.md)

## About Templates<a name="about-templates"></a>

### Using Built\-in Templates<a name="using-builtin-templates"></a>

MediaLive includes built\-in templates that you can access on the console\. Each template includes data for output groups and outputs, and most importantly, data for encoding video to meet specific use cases \(as specified in the template description\)\. 

When you use a built\-in template, all sections of the **Create channel** page are populated with data except for the inputs and output destinations sections\. 

Even though the templates are built\-in, you can choose to edit the existing fields and complete the empty fields\.

### Using Custom Templates<a name="using-custom-templates"></a>

You or another person in your organization may have created custom templates\. A custom template might contain nearly all the data that is required to create a complete channel, or it might contain only portions of the data\. To create a custom template, see [Creating a Custom Template](creating-custom-template.md)\. 

Typically, templates are created in order to be shared among different users\.

If your organization uses templates, you must obtain the templates you will use from the person who created the templates\. You must store them in a folder on the computer where you are working on the MediaLive console\. This folder is the "custom template location\." You perform this task in your computer's filesystem, outside of MediaLive\. 

When you use a custom template, MediaLive populates all sections of the **Create channel** page are populated with data from the template, except for the input data\. Even if the template includes input data, that data will not be pulled into the **Create channel** page\. 

You can edit the existing fields and complete the empty fields as needed\.

## About Cloning<a name="about-cloning"></a>

Cloning lets you use an existing channel as the basis for a new channel\. 

When you clone an existing channel, all sections of the **Create channel** page are populated with the data from the cloned channel, except for the input data\. Input data is always left blank\. 

You can edit the existing fields and complete the empty fields as needed\.