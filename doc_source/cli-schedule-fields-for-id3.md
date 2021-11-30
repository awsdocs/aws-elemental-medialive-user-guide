# ID3 metadata item – payload<a name="cli-schedule-fields-for-id3"></a>

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
    },
    "HlsTimedMetadataSettings": {
     "Id3": "string"
    }
   }
  }
 ]
}
```

## Example<a name="json-id3-example"></a>

This example of a request creates ID3 metadata to be inserted at 13:35:59 UTC\.

```
{
  "ChannelId": "999999",
  "Creates": {
  "ScheduleActions": [
    {
      "ScheduleActionStartSettings": {
        "FixedModeScheduleActionStartSettings": {
          "Time": "2019-01-02T13:35:59Z"
        }
      },
      "ActionName": "id3-metadata.2019-01-02T13:35:59Z",
      "ScheduleActionSettings": {
        "HlsTimedMetadataSettings": {
          "Id3": "SUQzBAAAAAAAFVRYWFgAAAALAABIZWxsbyBXb3JsZA=="
          }
        }
      }
    ]
  }
}
```