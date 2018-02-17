# Option 1: Send all AWS Elemental MediaLive Events to an Email Address<a name="option-1"></a>

This option shows how to set up is to send all events to a single email address\. The drawback of this setup is that the email account will receive a large volume of emails\. Therefore this setup is not recommended in a production environment\. 

You must perform this setup in each region where channels are running\.

## Step 1: Create a Subscription<a name="option-1-1"></a>

You create a subscription to set up a specific email address so that it automatically receives email notifications when any event occurs in AWS Elemental MediaLive\. You need to identify an email recipient for the emails\.

We illustrate this procedure with the example of setting up to send emails with the sender appearing as "MediaLive" and the subject line as "MediaLive\_alert"\.

1. Sign in to the AWS Management Console and open the Amazon Simple Notification Service console\.

1. In the navigation panel, choose **SNS dashboard**, then choose **Topics**\.

1. On the **SNS dashboard** page, choose **Create new topic**\.

1. In **Topic** name, type the name you want for the subject of the email\. For example, "MediaLive\_alert"\.

1. In Display name type the name you want for the sender of the email\. For example "MediaLive"\.

1. Choose **Create topic**\.

1. SNS creates the topic and displays the ARN in the **Topic details** panel\. For example, arn:aws:sns:us\-west\-2:111122223333:MediaLive, where 111122223333 is your AWS account\.

1. Copy this ARN to your clipboard\. 

1. In the navigation panel, choose **Subscriptions**\.

1. In the **Subscriptions** page, choose **Create subscriptions**\.

1. In the **Create subscriptions** pane, in **Topic ARN**, type or paste the ARN\.

1. In **Protocol**, choose **Email**\.

1. In **Email address**, type the email address of the recipient\. You must be able to log onto this email account because you will be sending a confirmation email to this address\.

1. Choose **Create subscription**\.

   SNS sends a confirmation email to the address you specified\. 

1. Log onto that email account and display the email\. Choose the Confirm subscription link in the email to enable the subscription\. A confirmation window appears in a web browser\. You can close this window\.

## Step 2: Create a CloudWatch Rule<a name="option-1-2"></a>

You now create a rule that says "When CloudWatch receives any event from aws\.medialive, invoke the specified SNS topic – in other words, send an email to the subscribed email address\.

1. Sign in to the AWS Management Console and open the Amazon CloudWatch console\. 

1. On the navigation pane, choose **Events**\.

1. In **Welcome to CloudWatch Events**, choose **Create Rule**\.

1. In** Step 1**, in **Event Source**, choose **Event Pattern**\.

1. Change **Build event pattern to match** to **Custom event pattern**\.

1. In the entry box, type the following:

   ```
   {
     "source": [
       "aws.medialive"
     ]
   }
   ```

1. From the right\-hand panel, choose **Add target**\.

1. Choose **SNS topic**\.

1. In **Topic**, choose the topic you created, for example, "MediaLive\_alert"\.

1. Choose **Configure details**

1. In **Configure input**, choose **Matched event**\.

1. Type a name and optional description, then choose **Create rule**\. 

Now, whenever an alert occurs in AWS Elemental MediaLive, an event will be sent to Amazon CloudWatch\. This event will trigger the rule that instructs CloudWatch to send an email to the email address specified in the SNS subscription\.