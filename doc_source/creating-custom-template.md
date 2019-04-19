# Creating a Custom Template<a name="creating-custom-template"></a>

You create a custom template by exporting the data from an existing \(and therefore validated\) channel\. MediaLive exports the data to a JSON file that you can use on the console \. 

**To create a custom template \(console\)**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Channels**\.

1. On the **Channels** page, choose the channel name \(not the radio button\)\.

1. On the details page, choose **Create custom template**\. Follow the prompts to save the channel as a template\. The template is a JSON file with the same name as the channel\. 

1. \(Optional\) Open the file in a suitable editor and make changes\. For example, you can change field values, add fields, and remove fields\. Be careful to maintain valid JSON\. 

1. Make the custom template available to the users who will need them\. Each user must store the template in a folder that is accessible from the computer where the user will work on the MediaLive console\. This task is performed outside of MediaLive\.

Users of MediaLive can use the template file on the console\.