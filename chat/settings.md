# Chat Settings
***

Returns hitbox chat settings.

| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/settings/:channel](/chat/settings.md#get-chatsettingschannel) | Get chat settings. |
| [POST /chat/settings/:channel](/chat/settings.md#post-chatsettingschannel) | Updates chat settings. |
| [GET /chat/clearimagelog/:channel](/chat/settings.md#get-clearimagelogchannel) | Clears Image Log. |
| [GET /chat/pm/:value](/chat/settings.md#get-chatpmvalue) | Set Whisper Settings. |


## `GET /chat/settings/:channel`

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | Users Auth Token. | 

Returns chat settings for `:channel`

### Example URL

https://www.hitbox.tv/api/chat/settings/test-account

### Example Response 

```javascript
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

```javascript
{
  "channel":"test-account",
  "sub_images":true
}
```

### Example Response
If successful

```javascript
{
  "user_id":"278723",
  "sub_images":true
}
```

If invalid auth (Broadcaster and Editor Only)

```javascript
{
    "success":false,
    "error":true,
    "error_msg":"unauthorized"
}
```

## `GET /chat/clearimagelog/:channel`

Clears Chat Image Log

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | Users Auth Token. | 

### Example URL

https://www.hitbox.tv/api/chat/clearimagelog/test-account?authToken=SuperSecret

### Example Response

```javascript
{
    "success":true,
    "error":false,
    "message":"success"
}
```

## `GET /chat/pm/:value`

Set whisper settings. `value` can be set to 1 (Disable) or 0 (Enable)

### Example URL

https://www.hitbox.tv/api/chat/pm/:value?authToken=SuperSecret

### Example Response

```javascript
{
    "success":true,
    "error":false,
    "message":"success"
}
```

Permission Denied

```javascript
{
    "success":false,
    "error":true,
    "error_msg":"permission_denied"
}
```