# Option 1: Send all MediaLive Events to an Email Address<a name="option-1"></a>

This option shows how to set up to send all events to a single email address\. The drawback of this setup is that the email account will receive a large volume of emails\. Therefore, we recommend that you don't use this setup in a production environment\. 

You must perform the following procedure in each region where channels are running\.

## Step 1: Create a Subscription<a name="option-1-1"></a>

Create a subscription to set up a specific email address so that it automatically receives email notifications when any event occurs in MediaLive\. You must identify an email recipient for the emails\.

In the following procedure, we use the example of "MediaLive\_alert" as the subject line and "MediaLive" as the sender of the email\. We create the subscription using the Amazon Simple Notification Service \(Amazon SNS\) console\.

**To create a subscription for email notifications \(Amazon SNS console\)**

1. Sign in to the AWS Management Console and open the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v2/home](https://console.aws.amazon.com/sns/v2/home)\.

1. In the navigation pane, choose **Topics**, and then choose **Create new topic**\.

1. In the **Create new topic** dialog box, for **Topic name**, type the name that you want for the subject line of the email, such as **MediaLive\_alert**\.

1. For **Display name**, type the name that you want for the sender of the email, such as **MediaLive**\.

1. Choose **Create topic**\.

1. Amazon SNS creates the topic and displays the ARN in the list of topics\. For example, `arn:aws:sns:us-west-2:111122223333:MediaLive`, where `111122223333` is your AWS account\.

1. Copy this ARN to your clipboard\. 

1. In the navigation pane, choose **Subscriptions**, and then choose **Create subscription**\.

1. On the **Subscriptions** page, choose **Create subscription**\.

1. In the **Create subscriptions** dialog box, for **Topic ARN**, type or paste the ARN\.

1. For **Protocol**, choose **Email**\.

1. For **Endpoint**, type the email address of the recipient\. You must be able to log on to this email account because Amazon SNS sends a confirmation email to this address\.

1. Choose **Create subscription**\.

   Amazon SNS sends a confirmation email to the address that you specified\. 

1. Log on to that email account, and display the email\. Choose the "Confirm subscription" link in the email to enable the subscription\. A confirmation window appears in a web browser\. You can close this window\.

## Step 2: Create a Rule<a name="option-1-2"></a>

You now create a rule in Amazon CloudWatch that says, "When CloudWatch receives any event from aws\.medialive, invoke the specified SNS topic\." In other words, you create a rule that sends an email to the subscribed email address\.

**To create a rule \(Amazon CloudWatch console\)**

1. Sign in to the AWS Management Console and open the CloudWatch console at [https://console\.aws\.amazon\.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/)\.

1. In the navigation pane, choose **Events**\.

1. On the **Welcome to CloudWatch Events** page, choose **Create rule**\.

1. On the **Step 1** page, in **Event Source**, choose **Event Pattern**\.

1. Change **Build event pattern to match** to **Custom event pattern**\.

1. In the box, type the following:

   ```
   {
     "source": [
       "aws.medialive"
     ]
   }
   ```

1. On the pane on the right, choose **Add target**\.

1. Choose **SNS topic**\.

1. For **Topic**, choose the topic that you created, for example, **MediaLive\_alert**\.

1. In **Configure input**, choose **Matched event**\.

1. Choose **Configure details**\.

1. Type a name and optional description, and then choose **Create rule**\. 

Now, whenever an alert occurs in MediaLive, an event will be sent to Amazon CloudWatch\. This event will trigger the rule that instructs CloudWatch to send an email to the email address that you specified in the SNS subscription\.