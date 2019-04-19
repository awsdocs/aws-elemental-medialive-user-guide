# JSON Payload for Combining Create and Delete<a name="schedule-create-and-delete-json"></a>

To combine a batch of creates and deletes, include both a `Creates` section and a `Deletes` section in the JSON payload\. 

In this example, the payload in the `Deletes` section removes an action to activate an image overlay because it has an incorrect start time\. The action is named `overlay-21`\. The payload in the `Creates` section inserts that action again, this time with the correct start time\.

Even though the `Creates` section appears first in the JSON payload, MediaLive always executes the delete actions first\. 

In this action, the delete action and the create action have the same `ActionName`\. The name is being reused because the batch is a "delete and replace\." But you could assign a different name to the create action:

```
{
  "ChannelId": "999999",
  "Creates": {
  "ScheduleActions": [
    {
      "ScheduleActionStartSettings": {
        "FixedModeScheduleActionStartSettings": {
          "Time": "2018-05-21T20:42:19.000Z"
        }
      },
      "ActionName": "overlay-21",
      "ScheduleActionSettings": {
        "StaticImageActivateSettings": {
          "Image": {
          "PasswordParam": "imagespassword",
          "Uri": "s3ssl://banners/banner_A/high-res.bmp",
          "Username": "medialiveoperator"
          },
          "ImageY": 300,
          "FadeIn": 1500,
          "ImageX": 200,
          "Width": 800,
          "Opacity": 60,
          "Layer": 1,
          "Height": 900
          }
        }
      }
    ]
  },
  "Deletes": {
       "ActionNames": [
          "overlay-21"
        ]
    }
}
```