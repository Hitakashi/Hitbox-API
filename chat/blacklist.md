# Chat Word Blacklist
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/blacklist/:channel](/chat/blacklist.md#get-chatblacklistchannel) | Returns channels chat blacklist. |
| [POST /chat/blacklist/:channel](/chat/blacklist.md#post-chatblacklistchannel) | Updates channels chat blacklist. |

## `GET /chat/blacklist/:channel`

Returns the `channel` chat blacklist. Does not need authentication.

### Example URL

https://www.hitbox.tv/api/chat/blacklist/:channel

### Example Response 

```json
[
  "example.com",
  "superlongthingtonottrigger"
]
```

## `POST /chat/blacklist/:channel`

Updates `channel` blacklist.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

### Example URL

https://www.hitbox.tv/api/chat/blacklist/test-account?authToken=123

### Example POST Payload

```json
{
	"blacklist":["screenshooter.eu"]
}
```

### Example Response 

```json
saved
```
