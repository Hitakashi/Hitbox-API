# Overall Stream Stats API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /streamoverallstats/:user/:startTime/:endTime](/channel/steamoverallstats.md#get-streamoverallstatsuserstarttimeendtime) | Returns overall stream stats |

## `GET /streamoverallstats/:user/:startTime/:endTime`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns overall stream stats between `:startTime` and `:endTime` (These are Epoch time stamps)


### Example URL

https://www.hitbox.tv/api/streamoverallstats/test-account/1416182400000/1418860799000?authToken=SuperSecret

### Example Response 

```json
{
   "channel":"test-account",
   "startTime":1416182400000,
   "endTime":1418860799000,
   "totalUniques":5,
   "totalViewtime":4852,
   "totalViews":28,
   "totalCountries":1,
   "countries":{
      "unknown":{
         "uniques":5,
         "views":28,
         "viewtime":4852
      }
   }
}
```
