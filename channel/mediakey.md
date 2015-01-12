# Stream Key API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /mediakey/:channel](/channel/mediakey.md#get-mediakeychannel) | Gets stream key of channel. |
| [PUT /mediakey/:channel](/channel/mediakey.md#put-mediakeychannel) | Resets stream key of channel. |

## `GET /mediakey/:channel`

This returns a stream key for the provided user with the correct auth. 

| Parameter | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | User's Auth Token. | 

### Example URL

https://www.hitbox.tv/api/mediakey/test-account

### Example Response 

```json
{
  "streamKey":"HeyItsMyKey"
}
```

## `PUT /mediakey/:channel`

This resets the stream key for the specified channel.

| Parameter | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | User's Auth Token. | 

### Example URL

https://www.hitbox.tv/api/mediakey/test-account

### Example Response 

```json
{
  "streamKey":"HeyItsMyKey"
}
```
