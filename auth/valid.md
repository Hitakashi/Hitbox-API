# Valid Auth API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /auth/valid/:app](/auth/valid.md#get-authvalidapp) | Returns if the auth is valid. |

## `GET /auth/valid/:app`

Returns if the auth is valid. This only checks if the auth is valid but not if it's valid for an account. (Hopefully these tokens are always unqiue)

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| token | Yes | string | User's Auth Token |
| nocache | No | boolean | Returns fresh data from server? |

### Example URL

https://www.hitbox.tv/api/auth/valid/desktop?token=123

### Example Response 
```javascript
logged_in
````

If invalid auth:
```javascript
auth_failed
```
