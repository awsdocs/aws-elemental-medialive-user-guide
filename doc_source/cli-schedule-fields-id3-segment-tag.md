# ID3 segment tag item – payload<a name="cli-schedule-fields-id3-segment-tag"></a>

For information about the meaning and values for the fields in the following JSON, see the [AWS Elemental MediaLive API Reference](https://docs.aws.amazon.com/medialive/latest/apireference/)\.

```
{
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
	"HlsId3SegmentTaggingSettings": {
     "Tag": "string"
    }
   }
  }
 ]
}
```

## Example<a name="json-id3-segment-example"></a>

This example of a request creates an ID3 segment tag to be inserted starting at 13:35:59 UTC\. The tag contains the date, time, and number of the segment\.

```
{
  "ChannelId": "999999",
  "Creates": {
  "ScheduleActions": [
    {
      "ScheduleActionStartSettings": {
        "FixedModeScheduleActionStartSettings": {
          "Time": "2020-01-02T13:35:59Z"
        }
      },
      "ActionName": "id3-datetime-and-segment",
      "ScheduleActionSettings": {
        "HlsId3SegmentTaggingSettings": {
          "Tag": "$dt$-$sn$"
          }
        }
      }
    ]
  }
}
```