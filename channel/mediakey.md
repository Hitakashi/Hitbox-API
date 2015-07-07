# Stream Key API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /mediakey/:channel](/channel/mediakey.md#get-mediakeychannel) | Gets stream key of channel. |
| [PUT /mediakey/:channel](/channel/mediakey.md#put-mediakeychannel) | Resets stream key of channel. |

## `GET /mediakey/:channel`

| Parameter | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | User's Auth Token. | 

Get stream key for `:channel`

### Example URL

https://www.hitbox.tv/api/mediakey/test-account?authToken=SuperSecret

### Example Response 

```javascript
{
  "streamKey":"HeyItsMyKey"
}
```

## `PUT /mediakey/:channel`

| Parameter | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | User's Auth Token. | 

Reset stream key for `:channel`

### Example URL

https://www.hitbox.tv/api/mediakey/test-account?authToken=SuperSecret

### Example Response 

```javascript
{
  "streamKey":"HeyItsMyKey"
}
```
