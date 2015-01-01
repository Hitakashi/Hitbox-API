# Commercial Break API
***

| Endpoint | Description |
| ---- | --------------- |
| [POST /combreak/:channel/:count](/ws/combreak.md#post-combreakchannelcount) | Starts a commercial |

## `POST /combreak/:channel/:count`

Runs a commercial on the specified `:channel` with the amount of ads as `:count`

### Example URL

https://www.hitbox.tv/api/ws/combreak/test-account/1

### Example POST Payload

```json
{
   "authToken":"12312321312312"
}
```

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
