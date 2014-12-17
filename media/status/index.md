# 
***

What is the general description of what the endpoint does. You don't have to include parameters if the endpoint doesn't have them.

| Endpoint | Description |
| ---- | --------------- |
| [GET /media/status/:channel](/media/status/index.md#get-mediastatuschannel) | Returns simple information about the stream. |

## `GET /media/status/:channel`

Returns live status and viewers. (Viewer count is delayed)

### Example URL

https://www.hitbox.tv/api/media/status/test-account

### Example Response 

```json
{
  "media_is_live":"1",
  "media_views":"1111"
}
```
