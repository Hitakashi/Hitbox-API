# User
***

This API contains endpoints that describes the provided auth token.

| Endpoint | Description |
| ---- | --------------- |
| [GET /user/:user](/user/index.md#get-useruser) | Get user account information. |
| [PUT /user/:user](/user/index.md#put-useruser) | Updates account information. |
| [GET /user/access/:channel/:auth](/user/index.md#get-useraccesschannelauth) | Get access levels for the provided auth in the channel. |
| [GET /user/subscription/:channel/:auth](/user/index.md#get-usersubscriptionchannelauth) | Check if the given `:auth` is a subscriber to `:channel`. |
| [GET /user/list](/user/index.md#get-userlist) | Returns user list. |

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

## `PUT /user/:user`

Updates the current user.

As a general guideline for below passwords in POST if it's password change or email

| POST Data | Required? | Type | Description |
| --- | --- | --- | --- |
| user_name | Yes | string | Username |
| user_email | Yes | string | Email |
| user_password | No | string | Old Password |
| user_password_new | No | string | New Password |
| user_password2_new | No | string | Validate New Password |
| user_display_name | Yes | string | Must match user_name except in cases. |
| twitter_account | No | string | Twitter Account Handle |
| twitter_enabled | No | boolean | Twitter Enabled on Profile |

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | Users Auth Token. | 

### Example URL

https://www.hitbox.tv/api/user/test-account

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
   }
]
```
