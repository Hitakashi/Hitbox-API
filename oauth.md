# OAuth
***

This API is used for receiving  global messages to hitbox users.

| Endpoint | Description |
| ---- | --------------- |
| [GET /oauthaccess/:user](/oauth.md#get-oauthaccessuser) | Get Third Party OAuth Access |
| [POST /oauthaccess/:user](/oauth.md#post-oauthaccessuser) | Remove Application From Account |
| [GET /userfromtoken/:token](/oauth.md#get-userfromtokentoken) | Get User From Token |

## `GET /oauthaccess/:user`

Get list of third party applications that have access to `user`

### Example URL

https://www.hitbox.tv/api/oauthaccess/Test-Account?authToken=SuperSecret

### Example Response

```javascript
{
    "apps":[
        {
            "name":"Third Party Site",
            "description":"App Description"
        }
    ]
}
```

## `POST /oauthaccess/:user`

Remove applications from `user`

### Example URL

https://www.hitbox.tv/api/oauthaccess/Test-Account?authToken=SuperSecret

### Example Response

```javascript
{
    "error":false,
    "success":true
}
```

## `GET /userfromtoken/:token`

Get username a token belongs to.

### Example URL

https://www.hitbox.tv/api/userfromtoken/SuperSecret

### Example Response 

Token exists.

```javascript
{
    "user_name":"test-account"
}
```

Token doesn't exist.

```javascript
[]
```
