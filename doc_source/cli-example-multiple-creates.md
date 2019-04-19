# Combination of Create Actions<a name="cli-example-multiple-creates"></a>

Here is an example of a JSON body to pass into the `--creates` parameter of the `batch-update-schedule` AWS CLI command\. It contains two actions to create\. In this example, both actions are splice\_inserts, but in fact you can combine any number and any type of create actions:

```
{
    "ScheduleActions": [
      {
        "ScheduleActionSettings": {
          "Scte35SpliceInsertSettings": {
            "Duration": 1350000
            "SpliceEventId": 3
          }
        },
        "ActionName": "SpliceInsert-01",
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "2018-11-05T16:10:30.000Z"
          }
        }
      },
      {
        "ScheduleActionSettings": {
          "Scte35SpliceInsertSettings": {
            "Duration": 2700000,
            "SpliceEventId": 3
          }
        },
        "ActionName": "SpliceInsert-02",
        "ScheduleActionStartSettings": {
          "FixedModeScheduleActionStartSettings": {
            "Time": "2018-11-05T16:30:45.000Z"
          }
        }
      }
    ]
  }
```