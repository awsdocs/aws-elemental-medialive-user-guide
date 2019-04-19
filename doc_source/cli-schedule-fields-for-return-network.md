# Payload for a Return\-to\-Network Message<a name="cli-schedule-fields-for-return-network"></a>

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
        "Scte35ReturnToNetworkSettings": {
          }
        }
      }
    ]
  }
}
```

## Example<a name="json-return-network-example"></a>

This example of a request creates a return\-to\-network with a UTC start time of 20:42:19:

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
      "ActionName": "end_adavail_3708",
      "ScheduleActionSettings": {
        "Scte35ReturnToNetworkSettings": {
          }
        }
      }
    ]
  }
}
```