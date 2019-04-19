# Payload for a Deactivate Overlay Action<a name="cli-schedule-fields-for-deactivate-image"></a>

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
        "StaticImageDeactivateSettings": {
          "FadeOut": "integer",
          "Layer": "integer"
          }
        }
      }
    ]
  }
}
```

## Example<a name="json-deactivate-image-example"></a>

This example of a request creates an action to end an image overlay at 20:42:04\.000 \(UTC\) with a 500 millisecond fadeout that is added onto the end time, which means that the overlay will be invisible at 20:42:04\.500:

```
{
  "ChannelId": "999999",
  "Creates": {
  "ScheduleActions": [
    {
      "ScheduleActionStartSettings": {
        "FixedModeScheduleActionStartSettings": {
          "Time": "2018-05-21T20:42:04.000Z"
        }
      },
      "ActionName": "stop_overlay_029",
      "ScheduleActionSettings": {
        "StaticImageDeactivateSettings": {
          "FadeOut": 500,
          "Layer": 1
          }
        }
      }
    ]
  }
}
```