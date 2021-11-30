# Activate image action – payload<a name="cli-schedule-fields-for-activate-image"></a>

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
    "StaticImageActivateSettings": {
     "Duration": integer,
     "FadeIn": integer,
     "FadeOut": integer,
     "Height": integer,
     "Image": {
      "PasswordParam": "string",
      "Uri": "string",
      "Username": "string"
     },
     "ImageX": integer,
     "ImageY": integer,
     "Layer": integer,
     "Opacity": integer,
     "Width": integer
     }
    }
   }
  ]
 }
}
```

## Example<a name="json-activate-image-example"></a>

This example of a request creates an image overlay using a file that is stored in an Amazon S3 bucket\. The request doesn't include a duration and therefore doesn't include a fadeout\. Instead, the intention is to send a separate deactivate request at the appropriate time\. All the times are in milliseconds, and all the positioning values are in pixels:

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
      "ActionName": "corporate-logo-030",
      "ScheduleActionSettings": {
        "StaticImageActivateSettings": {
          "Image": {
          "PasswordParam": "corplogo!2312",
          "Uri": "s3ssl://DOC-EXAMPLE-BUCKET/logos/corporate/high-res.bmp",
          "Username": "medialiveoperator"
          },
          "ImageY": 300,
          "FadeIn": 1500,
          "ImageX": 200,
          "Width": 800,
          "Opacity": 60,
          "Layer": 1,
          "Height": 900
          }
        }
      }
    ]
  }
}
```