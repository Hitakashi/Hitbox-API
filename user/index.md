# User
***

This API contains endpoints that describes the provided auth token.

| Endpoint | Description |
| ---- | --------------- |
| [POST /user](/user/index.md#post-user) | Creates user account |
| [GET /user/:user](/user/index.md#get-useruser) | Get user account information. |
| [PUT /user/:user](/user/index.md#put-useruser) | Updates account information. |
| [GET /user/access/:channel/:auth](/user/index.md#get-useraccesschannelauth) | Get access levels for the provided auth in the channel. |
| [GET /user/subscription/:channel/:auth](/user/index.md#get-usersubscriptionchannelauth) | Check if the given `:auth` is a subscriber to `:channel`. |
| [GET /user/list](/user/index.md#get-userlist) | Returns user list. |
| [POST /user/:user/team/default](/user/index.md#post-useruserteamdefault) | Changes default team. |

## `POST /user`

This API does require a challenge and captcha from reCaptcha, So it might be impossible to externally create accounts.

| Paramater | Required? | Type | Description |
| --- | --- | --- | --- |
| user_name | Yes | string | User name to register |


### Example URL

https://www.hitbox.tv/api/user?user_name=test-account

### Example Post Payload

```json
{
   "user_email":"user@example.com",
   "user_password":"password",
   "user_password2":"password",
   "user_name":"test-account",
   "captcha":{
      "response":"",
      "challenge":""
   }
}
```

### Example Response

```json
user_created
```

## `GET /user/:user`

Returns account information about the user.

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | No | string | Users Auth Token. Used if wanting private user information. | 
| nocache | No | boolean | No clue. Server side switch probably. |

### Example URL

https://www.hitbox.tv/api/user/test-account

### Example Response

if authToken
```json
{
   "followers":"0",
   "user_id":"123",
   "user_name":"test-account",
   "user_status":"1",
   "user_logo":"\/static\/img\/channel\/test-account_53f4e837eb388_large.png",
   "user_cover":"\/static\/img\/channel\/cover_53fbf06572c78.png",
   "user_logo_small":"\/static\/img\/channel\/test-account_53f4e837eb388_small.png",
   "user_email":"example@example.com",
   "user_partner":null,
   "media_is_live":"0",
   "media_live_since":"2014-12-14 05:18:54",
   "twitter_account":"test-account",
   "twitter_enabled":"1",
   "livestream_count":"1"
}
```

else

```json
{
   "user_name":"test-account",
   "user_cover":"\/static\/img\/channel\/cover_53fbf06572c78.png",
   "user_status":"1",
   "user_logo":"\/static\/img\/channel\/test-account_53f4e837eb388_large.png",
   "user_logo_small":"\/static\/img\/channel\/test-account_53f4e837eb388_small.png",
   "user_is_broadcaster":true,
   "followers":"7",
   "user_partner":null,
   "user_id":"123",
   "is_live":"0",
   "live_since":"2014-12-14 05:18:54",
   "twitter_account":"test-account",
   "twitter_enabled":"1"
}
```

Channel without stream setup

```json
{
   "user_name":"Test-Account",
   "user_cover":null,
   "user_status":"1",
   "user_logo":"\/static\/img\/channel\/masta_52274f9e8159b_large.jpg",
   "user_logo_small":"\/static\/img\/channel\/masta_52274f9e8159b_small.jpg",
   "user_is_broadcaster":false,
   "followers":"0",
   "user_partner":null,
   "user_id":"1111111",
   "is_live":null,
   "live_since":null,
   "twitter_account":null,
   "twitter_enabled":null
}
```

## `PUT /user/:user`

Updates the current user.

As a general guideline for below passwords in POST if it's password change or email

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | Users Auth Token. | 

### Example URL

https://www.hitbox.tv/api/user/test-account

### Example POST Payload

```json
{
   "user_name":"test-account",
   "user_email":"test@example.com",
   "user_password":"myoldpassword",
   "user_password_new":"changingmypassword",
   "user_password2_new":"changingmypassword",
   "user_display_name":"test-Account",
   "twitter_account":"@test_account",
   "twitter_enabled":true
}
```

### Example Response

if authToken
```json
user_updated
```

## `GET /user/access/:channel/:auth`

Returns access levels for the auth in the provided channel.


### Example URL

https://www.hitbox.tv/api/user/access/test_channel/test_auth

### Example Response 

`user_id` = User ID

`access_user_id` = Channel User ID

```json
{
   "user_id":"123",
   "access_user_id":"124",
   "settings":"anon",
   "account":"anon",
   "livestreams":"anon",
   "partner":"anon",
   "broadcast":"anon",
   "videos":"anon",
   "recordings":"anon",
   "statistics":"anon",
   "inbox":"anon",
   "revenues":"anon",
   "chat":"anon",
   "following":"anon",
   "teams":"anon",
   "subscriptions":"anon",
   "admin":null,
   "superadmin":null,
   "isSubscriber":false,
   "isFollower":false
}
```

## `GET /user/subscription/:channel/:auth`

Returns access levels for the auth in the provided channel.


### Example URL

https://www.hitbox.tv/api/user/subscription/test_channel/test_auth

### Example Response 

```json
{
   "isSubscriber":false
}
```

## `GET /user/list`

Returns the user list.

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| q | no | string | User to seach for. | 
| limit | no | int | Doesn't seem to work. |

### Example URL

https://www.hitbox.tv/api/user/list

### Example Response

```json
[
   {
      "user_name":"test-account",
      "user_status":"1",
      "user_logo":"\/static\/img\/channel\/test-account_543fc6c30cbf5_large.jpg",
      "user_logo_small":"\/static\/img\/channel\/test-account_543fc6c30cbf5_small.jpg"
   },
   ...
]
```

## `POST /user/:user/team/default`

Changes default team that shows on your channel.

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | User's Auth Token | 

## Example URL

https://www.hitbox.tv/api/user/test-account/team/default

### Example POST Payload

```json
{
   "group_id":"123"
}
```

### Example Response

Again, Even if it fails to change the default group (Ex: Not even in the group):
```json
success
```
