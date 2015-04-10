# Chat Word Blacklist
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/blacklist/:channel](/chat/blacklist.md#get-chatblacklistchannel) | Returns channels chat blacklist. |
| [POST /chat/blacklist/:channel](/chat/blacklist.md#post-chatblacklistchannel) | Updates channels chat blacklist. |

## `GET /chat/blacklist/:channel`

Returns the `channel` chat blacklist.

### Example URL

https://www.hitbox.tv/api/chat/blacklist/test-account

### Example Response 

```json
[
  "example.com"
]
```

## `POST /chat/blacklist/:channel`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Updates `channel` blacklist

### Example URL

https://www.hitbox.tv/api/chat/blacklist/test-account?authToken=SuperSecret

### Example POST Payload

```json
{
	"blacklist":["example.com"]
}
```

### Example Response 

```json
saved
```
