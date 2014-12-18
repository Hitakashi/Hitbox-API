# Commercial Break API
***

| Endpoint | Description |
| ---- | --------------- |
| [POST /combreak/:channel/:count](/ws/combreak.md#post-combreakchannelcount) | Starts a commercial |

## `POST /combreak/:channel/:count`

This API totally ignores `channel` and `count` POST data and instead uses the data from the URL for `channel` and `count`

| POST Data | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| channel | No | string | Channel Name |
| count | No | string | Number of ads |

### Example URL

https://www.hitbox.tv/api/ws/combreak/test-account/1

### Example Response 

```json
{
   "method":"commercialBreak",
   "params":{
      "channel":"test-account",
      "count":"1",
      "delay":"0",
      "token":"authToken",
      "url":"http:\/\/hitbox.tv",
      "timestamp":1418876364
   }
}
```
