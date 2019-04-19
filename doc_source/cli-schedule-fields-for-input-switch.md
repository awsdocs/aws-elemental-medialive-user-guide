# Payload for an Input Switch Action<a name="cli-schedule-fields-for-input-switch"></a>

The following sections show the payload for fixed and follow input switch actions\. 

## Payload for a Fixed Input Switch Action<a name="json-fixed-switch"></a>

 For information about the meaning and values for the fields in the following JSON, see the [AWS Elemental MediaLive API Reference](https://docs.aws.amazon.com/medialive/latest/apireference/):

```
{
  "ChannelId": "string",
  "Creates": {
    "ScheduleActions": [
      {
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "string"
          }
        },
        "ActionName": "string",
        "ScheduleActionSettings": {
          "InputSwitchSettings": {
            "InputAttachmentNameReference": "string"
          }
        }
      }
    ]
  }
}
```

## Payload for a Follow Input Switch Action<a name="json-follow-switch"></a>

For information about the meaning and values for the fields in the following JSON, see the [AWS Elemental MediaLive API Reference](https://docs.aws.amazon.com/medialive/latest/apireference/):

```
{
  "ChannelId": "string",
  "Creates": {
    "ScheduleActions": [
      {
        "ScheduleActionStartSettings": {
          "FollowModeScheduleActionStartSettings": {
            "FollowPoint": "string",
            "ReferenceActionName": "string"
          }
        },
        "ActionName": "string",
        "ScheduleActionSettings": {
          "InputSwitchSettings": {
            "InputAttachmentNameReference": "string"
          }
        }
      }
    ]
  }
}
```

## Example 1<a name="json-switch-example"></a>

This example of a request switches to an input at a fixed time\. The input is the input attachment with the name **vod\_ward\_cars\_ad**\. This name was given to the input when the input was set up as an input attachment in this channel\. 

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
        "ActionName": "ad_002",
        "ScheduleActionSettings": {
          "InputSwitchSettings": {
            "InputAttachmentNameReference": "vod_ward_cars_ad"
          }
        }
      }
    ]
  }
}
```

## Example 2<a name="json-switch-example2"></a>

This example shows a request that contains two input switches\. The first switch is the same as example 1\. The second switch \(which starts at the second "`ScheduleActionStartSettings`" line\) is set up to follow the first switch\. The switch will occur when the previous action \(`ad_002`\) ends\. In order for a follow switch to work, the previous action must have an input that is a file input\. The second switch can be a file input or live input\. In this case, it is a live input, as the input name implies:

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
        "ActionName": "ad_002",
        "ScheduleActionSettings": {
          "InputSwitchSettings": {
            "InputAttachmentNameReference": "vod_ward_cars_ad"
          }
        }
      },
      {
        "ScheduleActionStartSettings": {
          "FollowModeScheduleActionStartSettings": {
            "FollowPoint": "END",
            "ReferenceActionName": "ad_002"
         }
       },
          "ActionName": "end_ad_block",
          "ScheduleActionSettings": {
            "InputSwitchSettings": {
              "InputAttachmentNameReference": "live_studio_feed"
          }
        }
      }
    ]
  }
}
```