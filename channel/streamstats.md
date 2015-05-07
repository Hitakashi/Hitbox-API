# Stream Stats API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /streamstats/:user/:startTime/:endTime](/channel/streamstats.md#get-streamstatsuserstarttimeendtime) | Returns stream stats |
| [GET /streamedseconds/:channel/:startDate/:endDate](/channel/streamstats.md#get-streamedsecondschannelstartdateenddate) | Returns seconds streamed |

## `GET /streamstats/:user/:startTime/:endTime`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns stream stats between `:startTime` and `:endTime`  (These are Epoch time stamps)

**Note**: Due to how long this API response is, the timeline arrays have been truncated to one array each.

### Example URL

https://www.hitbox.tv/api/streamstats/test-account/1416182400000/1418860799000?authToken=SuperSecret

### Example Response 

```json
{
   "channel":"test-account",
   "startTime":"1416182400000",
   "endTime":"1418860799000",
   "step":86400000,
   "maxviewer":2,
   "maxfollower":2,
   "maxregistered":2,
   "maxembed":0,
   "maxsubscriber":0,
   "maxandroid":0,
   "maxios":0,
   "maxchromecast":0,
   "maxweb":2,
   "totalads":0,
  "timeline":{
    "viewer":[
      [
        1427688900000,
        1
      ]
    ],
    "viewer_avg":[
      [
        1427688900000,
        1
      ]
    ],
    "follower":[
      [
        1427688900000,
        1
      ]
    ],
    "registered":[
      [
        1427688900000,
        1
      ]
    ],
    "embed":[
      [
        1427688900000,
        0
      ]
    ],
    "subscriber":[
      [
        1427688900000,
        0
      ]
    ],
    "android":[
      [
        1427688900000,
        0
      ]
    ],
    "ios":[
      [
        1427688900000,
        0
      ]
    ],
    "chromecast":[
      [
        1427688900000,
        0
      ]
    ],
    "web":[
      [
        1427688900000,
        1
      ]
    ],
    "ads":[
      [
        1427688900000,
        0
      ]
    ],
    "views":[
      [
        1427688900000,
        0
      ]
    ]
  }
}
```


## `GET /streamedseconds/:channel/:startDate/:endDate`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns streamed time in seconds between `:startDate` and `:endDate`

Both dates are epoch times.

### Example URL

https://www.hitbox.tv/api/streamedseconds/test-account/1428192000000/1430956800000

### Example Response

```json
{
   "channel":"test-account",
   "startTime":1428192000000,
   "endTime":1430956800000,
   "streamed_seconds":1412
}
```