# Chat Settings
***

Returns hitbox chat emoticons.

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/settings/:channel](/chat/settings.md#get-chatsettingschannel) | Get chat settings. |
| [POST /chat/settings/:channel](/chat/settings.md#post-chatsettingschannel) | Updates chat settings. |


## `GET /chat/settings/:channel`

Returns chat settings for the channel.

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | boolean | Users Auth Token. | 

### Example URL

https://www.hitbox.tv/api/chat/settings/test-account

### Example Response 

```json
{
  "sub_images":false
}
```

## `POST /chat/settings/:channel`

Returns chat settings for the channel.

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | boolean | Users Auth Token. | 

### Example URL

https://www.hitbox.tv/api/chat/settings/test-account

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
?
```

If invalid auth (Looks like only broadcasters/editors(?) can edit this.

```json
unauthorized
```
