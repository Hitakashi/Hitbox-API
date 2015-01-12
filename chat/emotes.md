# Chat Emotes
***

Returns hitbox chat emoticons.

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/icons/:user](/chat/emote_short.md#get-chaticonsuser) | Get channel emotes |

## `GET /chat/icons/:user`

Returns global chat emoticons.

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| premiumOnly | No | boolean | Show subscriber emotes if applicable. | 

### Example URL

https://www.hitbox.tv/api/chat/icons/:user

### Example Response 

```json
{
   "icons":{
      ":heart:":[
         "\/static\/img\/chat\/default\/heart.png",
         ":heart:",
         ":heart:"
      ],
      "...@":[
         "\/static\/img\/chat\/default\/tumbleweed.png",
         "..@",
         "..@"
      ],
      ...
   }
}
```
