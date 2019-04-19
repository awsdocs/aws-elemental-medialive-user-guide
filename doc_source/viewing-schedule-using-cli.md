# Viewing the Schedule \(AWS CLI\)<a name="viewing-schedule-using-cli"></a>

You can use the AWS CLI to view a list of the actions that are currently in the schedule for one channel:
+ Actions that have not yet been executed in the channel
+ Actions that have been executed within the last hour 

To view the schedule, you use the `DescribeSchedule` command\. This command is represented differently in different interfaces:
+ In the AWS CLI, the command is `describe-schedule`\.
+ In the API, the command is represented by an `HTTP GET` on `channels/channelId/schedule`\.
+ In the AWS SDKs, the command is represented by constructs that are suitable to that SDK language\. 

**To view actions \(AWS CLI\)**

1. Enter this command:

   aws medialive describe\-schedule \-\-channel\-id *value* \-\-max\-results value

1. To submit the command, press **Enter**\. The response appears on the screen\. 

1. If you used the `-max-results` option and the response included `NextToken`, enter the DescribeChannel command and pass the value of `NextToken` in `--next-token`\. For example:

   aws medialive describe\-schedule \-\-channel\-id *value* \-\-next\-token 3jhrprd0

1. To submit the command, press **Enter**\. The response appears on the screen\. 

## Example<a name="viewing-schedule-using-cli-example"></a>

The JSON body of the command *response* is similar to that of the `BatchUpdateSchedule` command *request*\.

This example of a response shows the following actions:
+ An action with the `ActionName` "**corporate\_logo\_029**" to activate an image overlay in layer 1 at 20:30:00 UTC
+ An action with the `ActionName` "**stop\_overlay\_029**" to deactivate the overlay in layer 1 at 20:42:04 UTC
+ An action with the `ActionName` "**adavail\_3708**" to insert a splice\_insert at the same time as the deactivate action
+ An action with the `ActionName` "**end\_adavail\_3708**" to return\-to\-network 15 seconds later, at 20:42:19 UTC
+ An action with the `ActionName` "**corporate\_logo\_030**" to reactivate the same overlay in layer 1 at the same time as the return

This schedule describes a workflow where you generally show your corporate logo, but you remove it at the start of each ad avail and then display it again at the end of the ad avail:

```
 {
  "NextToken": "3jhrprd0",
      "ScheduleActions": [
      {
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "2018-05-21T20:30:00.000Z"
          }
        },
        "ActionName": "corporate_logo_029",
        "ScheduleActionSettings": {
          "StaticImageActivateSettings": {
            "Image": {
            "PasswordParam": "corplogo!2312",
            "Uri": "s3ssl://logos/corporate/high-res.bmp",
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
      },
      {
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "2018-05-21T20:42:04.000Z"
          }
        },
        "ActionName": " stop_overlay_029",
        "ScheduleActionSettings": {
          "StaticImageDeactivateSettings": {
            "FadeOut": 1500,
            "Layer": 1
          }
        }
      },
      {
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "2018-05-21T20:42:04.000Z"
          }
        },
        "ActionName": "adavail_3708",
        "ScheduleActionSettings": {
          "Scte35SpliceInsertSettings": {
            "SpliceEventId": 3708,
            "Duration": 1350000
          }
        }
      },
      {
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "2018-05-21T20:42:19.000Z"
          }
        },
        "ActionName": "end_adavail_3708",
        "ScheduleActionSettings": {
          "Scte35ReturnToNetworkSettings": {
            "SpliceEventId": 3708
          }
        }
      },
      {
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "2018-05-21T20:42:19.000Z"
          }
        },
        "ActionName": "corporate_logo_030",
        "ScheduleActionSettings": {
          "StaticImageActivateSettings": {
            "Image": {
            "PasswordParam": "corplogo!2312",
            "Uri": "s3ssl://logos/corporate/high-res.bmp",
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
  }
```