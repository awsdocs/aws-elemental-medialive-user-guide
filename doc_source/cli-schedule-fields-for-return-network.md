# Return\-to\-network message – payload<a name="cli-schedule-fields-for-return-network"></a>

For information about the meaning and values for the fields in the following JSON, see the [AWS Elemental MediaLive API Reference](https://docs.aws.amazon.com/medialive/latest/apireference/)\.

```
{
 "ScheduleActions": [
  {
   "ScheduleActionStartSettings": {
    "FixedModeScheduleActionStartSettings": {
     "Time": "string"
    },
    "FollowModeScheduleActionStartSettings": {
     "FollowPoint": "enum",
     "ReferenceActionName": "string"
    },
    "ImmediateModeScheduleActionStartSettings": {
    }
   },
   "ActionName": "string",
   "ScheduleActionSettings": {
    "Scte35ReturnToNetworkSettings": {
     "SpliceEventId": integer                
    }
   }
  }
 ]
}
```

## Example<a name="json-return-network-example"></a>

This example of a request creates a return\-to\-network with a UTC start time of 20:42:19\.

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
      "ActionName": "end-adavail-3708",
      "ScheduleActionSettings": {
        "Scte35ReturnToNetworkSettings": {
          }
        }
      }
    ]
  }
}
```