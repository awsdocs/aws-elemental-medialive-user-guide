# JSON payload for delete actions<a name="cli-schedule-delete-json"></a>

 In the `Deletes` section, include the list of actions to delete by entering an array of `ActionNames`\. The array contains one or more action names\. You can obtain these action names using the `DescribeChannel` command \(see [Viewing the schedule \(AWS CLI\)](viewing-schedule-using-cli.md)\.

```
{
  "ChannelId": "string",
  "Deletes": {
      "ActionNames": [
          ""
    ]
  }
}
```

## Example<a name="cli-schedule-delete-json-example"></a>

This example of a request deletes the three actions identified by `ActionNames` that were assigned when you created the actions\.

```
{
  "ChannelId": "999999",
  "Deletes": {
      "ActionNames": [
          "stop-overlay-33",
          "adavail-3711",
          "end-adavail-3711"
      ]
  }
}
```