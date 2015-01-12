# Media Access API
***

| Endpoint | Description |
| ---- | --------------- |
| [POST /auth/media/:media_type/:media_name](/auth/media_access.md#post-authmediamedia_typemedia_name) | Returns access for video. |

## `POST /auth/media/:media_type/:media_name`

Returns if you can access a live stream or video.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

| POST Data | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth  Token |
| mediaPassword | If password protected | string | Password set on the media |
| media_name | Yes | string | Usually media_name or media_file from the /media/(live)|(video) endpoint |
| media_type | Yes | string | Type of media. Live or Video |

### Example URL

https://www.hitbox.tv/api/auth/media/video/321321321-492828234?authToken=123
https://www.hitbox.tv/api/auth/media/live/test-account?authToken=123

### Example POST Payload

```json
{
  "authToken":"13231323142412321",
  "mediaPassword":"123",
  "media_name":"test-account",
  "media_type":"live"
}
```

### Example Response 

This is used for when Staff members password protect streams for breaking TOS

```json
access_granted
```

If incorrect password or just joining a channel

```json
access_denied
```
