# Payload for a Pause Pipeline Action<a name="cli-schedule-fields-for-pause"></a>

For information about the meaning and values for the fields in the following JSON, see the [AWS Elemental MediaLive API Reference](https://docs.aws.amazon.com/medialive/latest/apireference/):

```
{
  "ChannelId": "8545690",
  "Creates": {
    "ScheduleActions": [
      {
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "2019-03-10T20:42:19Z"
          }
        },
        "ActionName": "pause_pipeline_0_now",
        "ScheduleActionSettings": {
          "PauseStateSettings": {
            "Pipelines": [
              {
                "PipelineId": "PIPELINE_0"
              }
            ]
          }
        }
      }
    ]
  }
}
```

## Example: Pausing One Pipeline<a name="json-pause-example"></a>

This example of a request pauses pipeline 0 at 20:42:19 UTC\. MediaLive always reads the command as "set the specified pipeline or pipelines to pause and set all other pipelines as unpaused\." 

```
{
  "ChannelId": "999999",
  "Creates": {
    "ScheduleActions": [
      {
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "2018-05-21T20:42:19Z"
          }
        },
        "ActionName": "pause_pipeline_0_now",
        "ScheduleActionSettings": {
          "PauseStateSettings": {
            "Pipelines": [
              {
                "PipelineId": "PIPELINE_0"
              }
            ]
          }
        }
      }
    ]
  }
}
```

## Example: Unpausing Both Pipelines<a name="json-unpause-example"></a>

This example of a request unpauses all pipelines that are currently paused\. Note that the `Pipelines` array is empty\. MediaLive interprets this empty array as "set all pipelines to unpaused":

```
{
  "ChannelId": "999999",
  "Creates": {
    "ScheduleActions": [
      {
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "2018-05-21T20:52:00Z"
          }
        },
        "ActionName": "unpause_pipeline_0",
        "ScheduleActionSettings": {
          "PauseStateSettings": {
            "Pipelines": [
              {
              }
            ]
          }
        }
      }
    ]
  }
}
```