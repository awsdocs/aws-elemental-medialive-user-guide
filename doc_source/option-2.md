# Option 2: Send Events for Specific Channels to an Email Address<a name="option-2"></a>

You can set up to send all events for a specific channel \(or channels\) to one email\. You must perform this setup in each region where channels are running\.

Create as many subscriptions and rules combinations as required\. Follow the steps for Option 1, with these differences:

+ When creating the SNS subscription, you may want to fine\-tune the topic, for example “MediaLive\_notifications\_channel\_1234567”\.

+ When creating the CloudWatch rule, you create a rule with an event pattern that identifies aws\.medialive as the “event source” and the ARN for the specific channel as “the resource” within that event source, as follows:

  ```
  {
    “source”: [
      “aws.medialive”
    ]
    “resources”: [
      “arn:aws:medialive:us-west-2:111122223333:channel:1234567”
    ] 
  }
  ```

 The resource is the ARN for the desired channel\. You can obtain this ARN from the channels list in the AWS Elemental MediaLive console\. 

This rule that says "When CloudWatch receives any event from aws\.medialive for channel 1234567, invoke the specified SNS topic – in other words, send an email to the subscribed email address\." 

 If desired, you can enter more than one channel in the resources section\. For example:

```
  “resources”: [
    “arn:aws:medialive:us-west-2:111122223333:channel:1234567”,
    “arn:aws:medialive:us-west-2:111122223333:channel:2223334”
  ]
```