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

```json
coming_soon_kappa,
i_need_to_wait_until_they_do_another_global_message
```

else

```json
nothing_found
```
