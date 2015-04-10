# Chat Moderator API
***

Editors can get a list of moderators, but they are disallowed access to add or remove.

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/moderators](/chat/moderators.md#get-chatmoderatorschannel) | Returns list of chat moderators. |
| [POST /chat/moderators](/chat/moderators.md#post-chatmoderatorschannel) | Add or Removes chat moderators. |
| [GET /chat/moderations](/chat/moderators.md#get-chatmoderationschannel) | Get channels you are a moderator in. |

## `GET /chat/moderators/:channel`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns list of chat moderators for `:channel`

### Example URL

https://www.hitbox.tv/api/chat/moderators/test-account?authToken=SuperSecret

### Example Response 

```json
{
   "request":{
      "this":"/chat/moderators/test-account"
   },
   "moderators":[
      {
         "user_id":"123",
         "user_name":"test-moderator",
         "user_logo":"/static/img/channel/test-moderator_531e431518a7_large.png"
      },
      ...
   ]
}
```

## `POST /chat/moderators/:channel`

Adds or removes chat moderators. Toggle `remove` for what action you want.

### Example URL

https://www.hitbox.tv/api/chat/moderators/test-account

### Example Response 


```json
{
   "user_name":"test-account",
   "authToken":"SuperSecret",
   "moderator":"test-moderator",
   "remove":false
}
```

## `GET /chat/moderations/:channel`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

### Example URL

https://www.hitbox.tv/api/chat/moderations/test-account?authToken=SuperSecret

### Example Response

```json
{
  "request":{
    "this":"/chat/moderations/test-account"
  },
  "moderations":[
    {
      "user_id":"12",
      "user_name":"test-broadcaster",
      "user_logo":"/static/img/channel/test-broadcaster_5394934904055_large.jpg"
    },
    ...
  ]
}
```
