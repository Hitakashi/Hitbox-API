# Global Message
***

This API is used for receiving  global messages to hitbox users.

| Endpoint | Description |
| ---- | --------------- |
| [GET /globalmessage](/README.md#get-globalmessage) | Get global announcements |

## `GET /globalmessage`

Receiving global message from hitbox.

### Example URL

https://www.hitbox.tv/api/globalmessage

### Example Response 

If global message

```javascript
{
  "message":"System Maintainence on February 3, 15:00 to 17:00 UTC"
}
```

else

```javascript
{
    "success":false,
    "error":true,
    "error_msg":"not_found"
}
```
