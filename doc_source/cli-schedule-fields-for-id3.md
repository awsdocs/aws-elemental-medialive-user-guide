# Payload for an ID3 Metadata Item<a name="cli-schedule-fields-for-id3"></a>

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
        "HlsTimedMetadataSettings": {
          "Id3": "string"
          }
        }
      }
    ]
  }
}
```

## Example<a name="json-id3-example"></a>

This example of a request creates ID3 metdata to be inserted at 13:35:59 UTC:

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
      "ActionName": "id3_metadata.2019-01-02T13:35:59Z",
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