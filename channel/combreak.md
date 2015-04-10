# Commercial Break API
***

| Endpoint | Description |
| ---- | --------------- |
| [POST /ws/combreak/:channel/:count](/channel/combreak.md#post-combreakchannelcount) | Starts a commercial |

## `POST /ws/combreak/:channel/:count`

Runs a commercial on the specified `:channel` with the amount of ads as `:count`

### Example URL

https://www.hitbox.tv/api/ws/combreak/test-account/1

### Example POST Payload

```json
{
   "authToken":"SuperSecret"
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
      "token":"SuperSecret",
      "url":"http://hitbox.tv",
      "timestamp":1418876364
   }
}
```
