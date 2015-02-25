# Chat Moderator API
***

Editors can get a list of moderators, but they are disallowed access to add or remove.

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/moderators](/chat/moderators.md#get-chatmoderators) | Returns list of chat moderators. |
| [POST /chat/moderators](/chat/moderators.md#post-chatmoderators) | Add or Removes chat moderators. |
| [GET /chat/moderations](/chat/moderators.md#get-chatmoderations) | Get channels you are a moderator in. |

## `GET /chat/moderators`

Returns list of chat moderators.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

### Example URL

https://www.hitbox.tv/api/chat/moderators/test-account?authToken=1232132131231231321

### Example Response 

```json
{
   "request":{
      "this":"\/chat\/moderators\/test-account"
   },
   "moderators":[
      {
         "user_id":"123",
         "user_name":"test-moderator",
         "user_logo":"\/static\/img\/channel\/test-moderator_531e431518a7_large.png"
      },
      ...
   ]
}
```

## `POST /chat/moderators`

Adds or removes chat moderators.

### Example URL

https://www.hitbox.tv/api/chat/moderators/test-account

### Example Response 

Toggle `remove` for what action you want.
```json
{
   "user_name":"test-account",
   "authToken":"12321321",
   "moderator":"test-moderator",
   "remove":false
}
```

## `GET /chat/moderation/:channel`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

### Example URL

https://www.hitbox.tv/api/chat/moderations/test-account?authToken=21312312

### Example Response

```json
{
  "request":{
    "this":"\/chat\/moderations\/test-account"
  },
  "moderations":[
    {
      "user_id":"1231231",
      "user_name":"test-broadcaster",
      "user_logo":"\/static\/img\/channel\/test-broadcaster_5394934904055_large.jpg"
    },
    ...
  ]
}
```
