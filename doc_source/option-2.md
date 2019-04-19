# Option 2: Send Events for Specific Channels to an Email Address<a name="option-2"></a>

You can set up a rule to send all events for a specific channel \(or channels\) to one email address\. You must perform this setup in each region where channels are running\.

Create as many subscriptions and rules combinations as you need\. Follow the steps for [option 1](option-1.md#option-1.title), with these differences:
+ When creating the SNS subscription, you might want to add more detail to the topic, for example, **MediaLive\_notifications\_channel\_1234567**\.
+ When creating the CloudWatch rule, you create an event pattern that identifies `aws.medialive` as the event source and the ARN for the specific channel as the resource within that event source, as follows:

  ```
  {
    "source": [
      "aws.medialive"
    ],
    "resources": [
      "arn:aws:medialive:us-west-2:111122223333:channel:1234567"
    ] 
  }
  ```

The resource is the ARN for the channel\. You can obtain this ARN from the channels list on the MediaLive console\. 

This rule says, "When CloudWatch receives any event from `aws.medialive` for channel `1234567`, invoke the specified SNS topic\." In other words, the rule triggers an email that is sent to the subscribed email address\.

 You can choose to include more than one channel in the resources section, as shown in the following example:

```
  "resources": [
    "arn:aws:medialive:us-west-2:111122223333:channel:1234567",
    "arn:aws:medialive:us-west-2:111122223333:channel:2223334"
  ]
```