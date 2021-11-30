# Time\_signal message – payload<a name="cli-schedule-fields-for-time-signal"></a>

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
    "Scte35TimeSignalSettings": {
     "Scte35Descriptors": [
      {
       "Scte35DescriptorSettings": {
        "SegmentationDescriptorScte35DescriptorSettings": {
         "DeliveryRestrictions": {
          "ArchiveAllowedFlag": "enum",
          "DeviceRestrictions": "enum",
          "NoRegionalBlackoutFlag": "enum",
          "WebDeliveryAllowedFlag": "enum"
         },
         "SegmentNum": integer,
         "SegmentationCancelIndicator": "enum",
         "SegmentationDuration": integer,
         "SegmentationEventId": integer,
         "SegmentationTypeId": integer,
         "SegmentationUpid": "string",
         "SegmentationUpidType": integer,
         "SegmentsExpected": integer,
         "SubSegmentNum": integer,
         "SubSegmentsExpected": integer
        }
       }
      }
     ]
    }
   }
  }
 ]
}
```

## Example<a name="json-time-signal-example"></a>

This example of a request creates an action for a time\_signal with a UTC start time of 20:42:04\.000 and with a unique integer for `SegmentationEventId`\. For the restrictions fields, `NoRegionalBlackoutFlag` has a restriction set \(regional blackouts are in place\)\.

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
      "ActionName": "adavail-3708",
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