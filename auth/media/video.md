# Video Access API
***

| Endpoint | Description |
| ---- | --------------- |
| [POST /auth/media/video/:media_file](/auth/media.md#post-authmediavideomedia_file) | Returns access for video. |

## `POST /auth/media/video/:media_file`

Returns if you can access a certain video based on it's `media_file` from [/media/video endpoint](/media/video.md#get-mediavideouserlist)

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

| POST Data | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth  Token |
| media_name | Yes | string | media_file from [updatethis] |
| media_type | Yes | string | Type of media. Live or Video |

### Example URL

https://www.hitbox.tv/api/auth/media/video/321321321-492828234?authToken=123

### Example Response 

```json
access_granted
```
