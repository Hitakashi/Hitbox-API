# Chat Emotes
***

Returns hitbox chat emoticons.

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/icons/:user](/chat/emotes.md#get-chaticonsuser) | Get channel emotes |
| [GET /chat/icon/:icon_name](/chat/emotes.md#get-chaticonicon_name) | Get Icon Properties |
| [POST /chat/icons/:user](/chat/emotes.md#post-chaticonsuser) | Add emoji to channel |

## `GET /chat/icons/:user`

Returns global chat emoticons.

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| premiumOnly | No | boolean | Show subscriber emotes if applicable. | 

### Example URL

https://www.hitbox.tv/api/chat/icons/test-account

### Example Response 

```javascript
{
   "icons":{
      ":heart:":[
         "/static/img/chat/default/heart.png",
         ":heart:",
         ":heart:"
      ],
      "...@":[
         "/static/img/chat/default/tumbleweed.png",
         "..@",
         "..@"
      ],
      ...
   }
}
```

## `GET /chat/icon/:icon_name`

Returns properties about a chat emoji.

### Example URL

[https://www.hitbox.tv/api/chat/icon/:testemote:](https://www.hitbox.tv/api/chat/icon/:testemote:)


### Example Response

```javascript
{
   "icon":{
      "icon_id":"2320",
      "icon_name":":testemote:",
      "icon_short":":testemote:",
      "icon_short_alt":":testemote:",
      "icon_path":"/static/img/channel/Hitakashi_54ef883564dd4_large.png",
      "icon_date_added":"2015-03-08 01:13:07",
      "icon_premium_only":"1",
      "icon_enabled":"1",
      "icon_comment":""
   }
}
```

## `POST /chat/icons/test-account`

Adds emoji to user account.

### Example URL

https://www.hitbox.tv/api/chat/icons/test-account

### Example POST Payload

Create
```javascript
{
    "media_id":"test-account",
    "icon_name":"testEmote",
    "icon_path":"/static/img/chat/test-account/emotes/emoji_55f126c635c22.png",
    "authToken":"SuperSecret",
    "icon_premium":1
}
```

Delete
```javascript
{
    "media_id":"test-account",
    "icon_id":"14068",
    "authToken":"SuperSecret",
    "action":"delete"
}
```

### Example Response

```javascript
{
    "success":true,
    "error":false,
    "message":"success"
}
```