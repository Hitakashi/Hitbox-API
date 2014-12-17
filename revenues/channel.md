# Revenues Stats API
***

| Endpoint | Description |
| ---- | --------------- |
| [POST /revenues/channel/:user](/twitter.md#post-twitterpost) | Returns Revenues stats |

## `POST /revenues/channel/:user`

Returns stream stats between `:startTime` and `:endTime`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| endDate | Yes | Epoch | Epoch time stamp |
| startDate | Yes | Epoch | Epoch time stamp |

### Example URL

https://www.hitbox.tv/api/revenues/channel/test-account?authToken=123&endDate=1418860799&startDate=1416182400

### Example Response 

Not a partner and hitbox does not have sandbox, So :(
```json
{
   "request":{
      "this":"\/revenues\/channel\/test-account",
      "type":"channel",
      "user":"test-account"
   },
   "revenues":{
      "performance":null
   }
}
```
