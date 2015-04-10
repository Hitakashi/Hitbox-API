# Chat Settings
***

Returns hitbox chat emoticons.

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/settings/:channel](/chat/settings.md#get-chatsettingschannel) | Get chat settings. |
| [POST /chat/settings/:channel](/chat/settings.md#post-chatsettingschannel) | Updates chat settings. |


## `GET /chat/settings/:channel`

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | Users Auth Token. | 

Returns chat settings for `:channel`

### Example URL

https://www.hitbox.tv/api/chat/settings/test-account

### Example Response 

```json
{
  "user_id":"123",
  "sub_images":false,
  "whisper":true
}
```

## `POST /chat/settings/:channel`

Returns chat settings for the channel.

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | Users Auth Token. | 

### Example URL

https://www.hitbox.tv/api/chat/settings/test-account?authToken=SuperSecret

### Example Payload 

```json
{
  "channel":"test-account",
  "sub_images":true
}
```

### Example Response
If successful

```json
{
  "user_id":"278723",
  "sub_images":true
}
```

If invalid auth (Looks like only broadcasters/editors(?) can edit this.)

```json
unauthorized
```
