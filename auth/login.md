# Auth
***

Returns information about the auth token.

| Endpoint | Description |
| ---- | --------------- |
| [POST /auth/login](/auth/login.md#get-authlogin) | API has two uses, get an auth token and verify an auth token.  |

## `POST /auth/login`

An example text about what the endpoint returns.

| Parameter | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | Users auth token | 
| Second POST |  |  |
| login | yes | string | username |

### Example URL

https://www.hitbox.tv/api/auth/login

### Example Response 

```json
{
   "test":{
      ":test:":"test"
   }
}
```
