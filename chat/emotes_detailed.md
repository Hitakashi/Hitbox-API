# Chat Emotes
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/emotes/:user](/chat/emotes/index.md#get-exampleapi) | Get channel emotes |

## `GET /chat/emotes/:user`

This is a more detailed list than [/chat/icons/index.md](/chat/icons/index.md)

| Parameter | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | No | string | Users auth token. | 

### Example URL

https://www.hitbox.tv/api/chat/emotes/:user

### Example Response 

```json
[
   {
      "icon_id":"1",
      "icon_name":"angry",
      "icon_short":"&gt;:(",
      "icon_short_alt":":angry:",
      "icon_path":"\/static\/img\/chat\/default\/angry1.png",
      "category_id":"1",
      "category_name":"defaultfaces",
      "category_logo":"\/static\/img\/chat\/default\/smile4.png",
      "icon_premium_only":"0"
   },
   {
      "icon_id":"2",
      "icon_name":"derpsmile",
      "icon_short":"o.o",
      "icon_short_alt":"O.O",
      "icon_path":"\/static\/img\/chat\/default\/derp1.png",
      "category_id":"1",
      "category_name":"defaultfaces",
      "category_logo":"\/static\/img\/chat\/default\/smile4.png",
      "icon_premium_only":"0"
   }
   ...
]
```
