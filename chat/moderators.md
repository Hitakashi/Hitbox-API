# Chat Moderator API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/moderators](/chat/moderators.md#get-chatmoderators) | Returns list of chat moderators. |
| [POST /chat/moderators](/chat/moderators.md#post-chatmoderators) | Add or Removes chat moderators. |

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
