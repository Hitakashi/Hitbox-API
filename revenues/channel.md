# Revenues Stats API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /revenues/channel/:user](/channel.md#get-revenueschanneluser) | Returns Revenues stats |

## `GET /revenues/channel/:user`

Returns revenues for given channel between `startDate` and `endDate`

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
