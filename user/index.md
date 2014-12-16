# User
***

This API contains endpoints that describes the provided auth token.

| Endpoint | Description |
| ---- | --------------- |
| [GET /user/:user](/user/index.md#get-useruser) | Get user account information. |
| [GET /user/access/:channel/:auth](/user/index.md#get-useraccesschannelauth) | Get access levels for the provided auth in the channel. |

## `GET /user/:user`

Returns account information about the user.

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | No | string | Users Auth Token. Used if wanting private user information. | 
| nocache | No | boolean | No clue. Server side switch probably. |

### Example URL

https://www.hitbox.tv/api/user/:user

### Example Request

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

## `GET /user/access/:channel/:auth`

Returns access levels for the auth in the provided channel.


### Example URL

https://www.hitbox.tv/api/access/test_channel/test_auth

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
