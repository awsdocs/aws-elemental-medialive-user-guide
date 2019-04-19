# Payload for a Splice\_Insert Message<a name="cli-schedule-fields-for-splice-insert"></a>

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
        "Scte35SpliceInsertSettings": {
          "SpliceEventId": "integer",
          "Duration": "integer"
          }
        }
      }
    ]
  }
}
```

## Example<a name="json-splice-insert-example"></a>

This example of a request creates an action for a splice\_insert with a UTC start time of 20:42:04\.000\. It also has an `ActionName` that perhaps references an ad avail from your database, a unique integer for the splice event ID, and a duration of 1,350,000 kHz ticks \(15 seconds\):

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
      "ActionName": "adavail_3708",
      "ScheduleActionSettings": {
        "Scte35SpliceInsertSettings": {
          "SpliceEventId": 3708,
          "Duration": 1350000
          }
        }
      }
    ]
  }
}
```