# Deactivate motion graphic overlay – payload<a name="cli-schedule-fields-deactivate-mgi"></a>

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
    },
    "ImmediateModeScheduleActionStartSettings": {
    }
   },
   "ActionName": "string",
   "ScheduleActionSettings": {
    "MotionGraphicsImageDeactivateSettings": {
     }
    }
   }
  ]
 }
}
```

## Example<a name="json-deactivate-mgi-example"></a>

This example of a request creates an action to end a motion graphic overlay at 23:59:00\.000 \(UTC\)\. :

```
{
"ChannelId": "999999",
"Creates": {
 "ScheduleActions": [
  {
  "ScheduleActionStartSettings": {
   "FixedModeScheduleActionStartSettings": {
   "Time": "2018-05-21T23:59:00.000Z"
   },
   "ActionName": "deactivate-ticker-tape",
   "ScheduleActionSettings": {
    "MotionGraphicsImageDeactivateSettings": {
     }
    }
   }
  ]
 }
}
```