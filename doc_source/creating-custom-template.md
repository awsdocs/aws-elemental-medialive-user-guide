# Creating a Custom Template<a name="creating-custom-template"></a>

You can create a custom template by exporting the data from an existing \(and therefore validated\) channel\. The data is exported to a JSON file that you can then use with the console or with the CLI or REST API\. 

1. On the console, choose **Channels** in the navigation pane\.

1.  In the **Channel** page, select the channel name \(not the radio button\)\.

1. On the details page, choose **Create custom template**\. A dialog appears\. This dialog belongs to the operating system of the computer where you are working on the AWS Elemental MediaLive console\. Follow the prompts to save the channel as a template\. The template is a JSON file with the same name as the channel\. 

1. You can optionally open the file in a suitable editor and make changes: change field values, add fields, remove fields\. Be careful to maintain valid JSON\. 

1. Finally, make the custom templates available to the users who will need them\. Each user must put the templates in a folder that is accessible from the computer where the user will work on the AWS Elemental MediaLive console\. This task is performed outside of AWS Elemental MediaLive\.

Users of AWS Elemental MediaLive can use the template file with the console or with the CLI or REST API\.

+ When using with the console, all the data from the file *except* for the input data appears on the **Create channel **page\.

+ When using with the CLI or REST API, all the data in the file is used\.