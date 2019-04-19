# Payload for a Time\_Signal Message<a name="cli-schedule-fields-for-time-signal"></a>

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
          "Scte35TimeSignalSettings": {
            "Scte35Descriptors": [
            {
                "Scte35DescriptorSettings": {
                  "SegmentationDescriptorScte35DescriptorSettings": {
                    "SubSegmentsExpected": "integer",
                    "SegmentationEventId": "integer",
                    "SegmentationDuration": "integer",
                    "SegmentationCancelIndicator": "enum",
                    "SubSegmentNum": "integer",
                    "SegmentationUpidType": "integer",
                    "SegmentNum": "integer",
                    "SegmentationCancelIndicator": "enum",
                    "DeliveryRestrictions": {
                      "DeviceRestrictions": "enum",
                      "WebDeliveryAllowedFlag": "enum",
                      "NoRegionalBlackoutFlag": "enum",
                      "ArchiveAllowedFlag": "enum"
                    },
                    "SegmentationUpid": "string",
                    "SegmentationTypeId": "integer",
                    "SegmentsExpected": "integer"
                  }
                }
              }
            ]
          }
        }
      }
    ]
  }
}
```

## Example<a name="json-time-signal-example"></a>

This example of a request creates an action for a time\_signal with a UTC start time of 20:42:04\.000 and with a unique integer for `SegmentationEventId`\. For the restrictions fields, `NoRegionalBlackoutFlag` has a restriction set \(regional blackouts are in place\):

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
        "Scte35TimeSignalSettings": {
          "Scte35Descriptors": [
          {
            "Scte35DescriptorSettings": {
              "SegmentationDescriptorScte35DescriptorSettings": {
                "SubSegmentsExpected": 0,
                "SegmentationEventId": 7054,
                "SegmentationDuration": 1350000,
                "SegmentationCancelIndicator": 0,
                "SubSegmentNum": 0,
                "SegmentationUpidType": 12,
                "SegmentNum": 0,
                "SegmentationCancelIndicator": "SEGMENTATION_EVENT_NOT_CANCELED",
                "DeliveryRestrictions": {
                  "DeviceRestrictions": "NONE",
                  "WebDeliveryAllowedFlag": "WEB_DELIVERY_ALLOWED",
                  "NoRegionalBlackoutFlag": "REGIONAL_BLACKOUT",
                  "ArchiveAllowedFlag": "ARCHIVE_ALLOWED"
                },
                "SegmentationUpid": "4a414e3136494e4155303031",
                "SegmentationTypeId": 52,
                "SegmentsExpected": 0
                  }
                }
              }
            ]
          }
        }
      }
    ]
  }
}
```