# OAuth
***

This API is used for receiving  global messages to hitbox users.

| Endpoint | Description |
| ---- | --------------- |
| [GET /oauthaccess/:user](/oauth.md#get-oauthaccessuser) | Get Third Party OAuth Access |
| [POST /oauthaccess/:user](/oauth.md#post-oauthaccessuser) | Remove Application From Account |
| [GET /userfromtoken/:token](/oauth.md#get-userfromtokentoken) | Get User From Token |
| [OAuth Flow](/oauth.md#oauth-flow) | OAuth Flow |

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

## `OAuth Flow`

You will need to setup a server that can handle redirects from the hitbox API after authorization and a ``app_token`` and ``app_secret``, which can be generated from your hitbox account tab.

### Login

Send the user to the hitbox API Authentication Page:

https://api.hitbox.tv/oauth/login?app_token=app_token

You should then handle three types of flows:

### Request Tokens

If the user hasn't already authenticated with your application and accepts authorization, the user will be redirected to:

https://redirect_uri?request_token=request_token.

#### Exchange

Once the user is redirected, You then need to exchange the ``request_token`` for an ``authToken``. To do this you need to send the following request:

##### `POST /oauth/exchange`

###### Payload

```json
{
    "request_token":"",
    "app_token":"",
    "hash":""
}
```
The ``hash`` value is a Base64 Encode of of the ``app_token`` and ``app_secret``. As an example, You can open up Chrome/Firefox Developer Tool go to the console and type ``btoa(app_token+app_secret);`` and the result will be your ``hash``.

You will then get back either two responses:

###### Success

This ``access_token`` is the equivalent of a regular ``authToken``. You are now able to use this on the hitbox API for the authentication user.

```json
{
    "access_token":""
}
```

###### Failure

```
authentication_failed
```

### Auth Token

If the user has already authenticated with your application and you exchanged the request_token, the hitbox API will skip the login screen. The user will be redirected with an ``authToken``:

https://redirect_uri?authToken=authToken

Note: You can add force_auth=true to the URL query to force login again.

### Errors

The hitbox API will redirect to the following URL when there's an error with authorization. (EX: User Canceled)

https://redirect_uri?error=error


