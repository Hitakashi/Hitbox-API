# Video Access API
***

| Endpoint | Description |
| ---- | --------------- |
| [POST /auth/media/:media_type/:media_name](/auth/media.md#post-authmediamedia_typemedia_name) | Returns access for video. |

## `POST /auth/media/:media_type/:media_name`

Returns if you can access a live stream or video.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

| POST Data | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth  Token |
| media_name | Yes | string | Usually media_name or media_file |
| media_type | Yes | string | Type of media. Live or Video |

### Example URL

https://www.hitbox.tv/api/auth/media/video/321321321-492828234?authToken=123
https://www.hitbox.tv/api/auth/media/live/test-account?authToken=123

### Example Response 

This doesn't seem fully implemented, They are probably going to add subscriber only VODs or Streams.

```json
access_granted
```
