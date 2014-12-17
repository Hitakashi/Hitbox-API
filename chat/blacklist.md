# Chat Word Blacklist
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/blacklist/:channel](/chat/blacklist.md#get-chatblacklist) | Returns channels chat blacklist. |

## `GET /chat/blacklist/:channel`

Returns the channels chat blacklist. Does not need authentication.

### Example URL

https://www.hitbox.tv/api/chat/blacklist/:channel

### Example Response 

```json
[
  "example.com",
  "superlongthingtonottrigger"
]
```
