#Media Status API 
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /media/status/:channel](/media/views.md#get-mediastatuschannel) | Returns simple information about the stream. |
| [GET /media/views/:channel](/media/views.md#get-mediaviewschannel) | Returns total view count. |

## `GET /media/status/:channel`

Returns live status and viewers. (Viewer count is delayed)

### Example URL

https://www.hitbox.tv/api/media/status/test-account

### Example Response 

```javascript
{
  "media_is_live":"1",
  "media_views":"1111"
}
```

## `GET /media/views/:channel`

Returns total view count, this is NOT live viewer count.

### Example URL

https://www.hitbox.tv/api/media/views/test-account

### Example Response

```javascript
{
  "total_live_views":"92718"
}
```
