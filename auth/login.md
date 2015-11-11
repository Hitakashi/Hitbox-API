# Auth API
***

Returns information about the auth token.

| Endpoint | Description |
| ---- | --------------- |
| [POST /auth/login](/auth/login.md#post-authlogin-auth) | Returns account information for the provided login. |
| [POST /auth/login](/auth/login.md#post-authlogin-info) | Returns account information for the provided auth token. |
| [POST /auth/token](/auth/login.md#post-authtoken) | Returns an auth token.

## `POST /auth/login (Auth)`

Sending a POST request with the below data returns account information.

### Example URL

https://www.hitbox.tv/api/auth/login

### Example POST Payload

```javascript
{
   "login":"test-account",
   "pass":"thisismypassword",
   "rememberme":""
}
```

### Example Response 

Correct credentials:
```javascript
{
  "user_id": "1",
  "user_name": "masta",
  "user_logo": "/static/img/channel/masta_56413fc1455f6_large.png",
  "user_logo_small": "/static/img/channel/masta_56413fc1455f6_small.png",
  "user_banned": "\u0000",
  "user_partner": null,
  "user_banned_channel": "0",
  "superadmin": "0",
  "livestream_count": "1",
  "followers": "19",
  "authToken": "SuperSecret",
  "login": "true",
  "data": {
    "user_id": "278723",
    "user_name": "masta",
    "user_logo": "/static/img/channel/masta_56413fc1455f6_large.png",
    "user_logo_small": "/static/img/channel/masta_56413fc1455f6_small.png",
    "user_banned": "\u0000",
    "user_partner": null,
    "user_banned_channel": "0",
    "superadmin": "0",
    "livestream_count": "1",
    "followers": "19",
    "authToken": "SuperSecret",
    "login": "true",
    "app": "desktop"
  },
  "access": "all",
  "app": "desktop"
}
```

Incorrect:
Will return a HTTP 400 Bad Request and response:

```javascript
auth_failed
```

## `POST /auth/login (Info)`

### Example URL

https://www.hitbox.tv/api/auth/login

### Example POST Payload

```javascript
{
  "app":"desktop",
  "authToken":"SuperSecret"
}
```

### Example Response 

Correct Auth Token:
```javascript
{
   "user_id":"111",
   "user_name":"test-account",
   "user_logo":"/static/img/channel/test-account_53f4e837eb388_large.png",
   "user_logo_small":"/static/img/channel/test-account_53f4e837eb388_small.png",
   "user_banned":"0",
   "user_banned_channel":"0",
   "superadmin":"0",
   "livestream_count":"1",
   "followers":"7",
   "authToken":"SuperSecret",
   "login":"true",
   "data":{
      "app":"desktop",
      "user_id":"123",
      "user_name":"test-account",
      "user_logo":"/static/img/channel/test-account_53f4e837eb388_large.png",
      "user_logo_small":"/static/img/channel/test-account_53f4e837eb388_small.png",
      "user_banned":"0",
      "superadmin":"0",
      "livestream_count":"1",
      "followers":"7",
      "authToken":"SuperSecret",
      "login":"true"
   },
   "access":"all",
   "app":"desktop"
}
```

Incorrect:
Will return a HTTP 400 Bad Request and response:

```javascript
auth_failed
```

## `POST /auth/token`

Sending a POST request with the below data returns an auth token for the account. `app` is option. The server will default to desktop.

### Example URL

https://www.hitbox.tv/api/auth/token

### Example POST Payload

```javascript
{
   "login":"test-account",
   "pass":"thisismypassword",
   "app":"desktop"
}
```

### Example Response

```javascript
{
   "authToken":"SuperSecret"
}
```
