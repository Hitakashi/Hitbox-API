# Team API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /team/:teamname](/team/team.md#get-teamteamname) | Get information about teams. |
| [POST /team](/team/team.md#post-team) | Creates a team |
| [PUT /team/:teamname/:username](/team/team.md#put-teamteamnameusername) | Updates a team |
| [UPDATE /team/:teamname/:username](/team/team.md#update-teamteamnameusername) | Accepts Invite |
| [DELETE /team/:teamname/:username](/team/team.md#delete-teamteamnameusername) | Kicks a user or removes yourself from a team |

## `GET /team/:teamname`

Return members and team information.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| nocache | No | boolean | Server Side Switch? |
| limit | No | int | Limits the results. Only limits livestream & video count. |
| liveonly | No | boolean | Only shows live only livestream channels if media=true and media_type is live. |
| media | No | boolean | Shows the media object if set to true |
| media_type | No | live or video | Enables showing of livestream or video objects in media. media must be true |
| filter | No | recent or popular | Sorts the media objects. |

### Example URL

https://www.hitbox.tv/api/team/thebestteam

### Example Response 

```javascript
{
   "info":{
      "group_id":"123",
      "founder_name":"Glorious-Leader",
      "group_name":"TheBestTeam",
      "group_display_name":"TheBestTeam",
      "group_text":"We rule. Obviously.",
      "group_logo_small":"/static/img/teams/logo_52d4870d92afaa_small.jpg",
      "group_logo_large":"/static/img/teams/logo_52d8704d92afaa_large.jpg",
      "group_cover":"/static/img/teams/cover_52d870a3e19343.jpg",
      "members_total":2
   },
   "members":[
      {
         "followers":"0",
         "user_id":"157",
         "user_name":"test-account",
         "user_status":"1",
         "user_logo":"/static/img/channel/test-account_53867c57ba993_large.jpg",
         "user_cover":null,
         "user_logo_small":"/static/img/channel/test-account_53867c57ba993_small.jpg",
         "user_partner":null,
         "admin":null,
         "enabled":"1",
         "group_role":"member",
         "is_default":"1",
         "revenues_enabled":null,
         "group_accepted":true
      },
      {
         "followers":"46",
         "user_id":"158",
         "user_name":"Glorious-Leader",
         "user_status":"1",
         "user_logo":"/static/img/channel/Glorious-Leader_52d334823811d_large.png",
         "user_cover":"/static/img/channel/cover_532ca1307ac13.jpg",
         "user_logo_small":"/static/img/channel/Glorious-Leader_52d334823811d_small.png",
         "user_partner":null,
         "admin":"1",
         "enabled":"1",
         "is_default":"1",
         "revenues_enabled":null,
         "group_role":"admin",
         "group_accepted":true
      }
   ]
}
```

If media=true and media_type is set, there will be the following javascript between `info` and `members` which will be filled depending on the media_type.

```javascript
"media": {
   "livestream": [],
   "video": []
},
```

The livestream array will be filled with:

```javascript
{
   "media_display_name":"Test-Account",
   "media_status":"Another Title!",
   "media_name":"test-account",
   "category_name":"DmC Devil May Cry",
   "media_views":"132",
   "media_countries":[
      "US"
   ],
   "media_live_since":"2015-03-19 18:15:34",
   "media_is_live":"1",
   "user_logo":"/static/img/channel/test-account_54f988997d191_large.jpg",
   "user_logo_small":"/static/img/channel/test-account_54f988997d191_small.jpg",
   "user_partner":"1",
   "media_offline_id":null,
   "media_id":1",
   "media_duration_format":"00:00:00",
   "category_logo_large":"",
   "media_thumbnail":"/static/img/media/live/test-account_mid_000.jpg",
   "media_thumbnail_large":"/static/img/media/live/test-account_large_000.jpg",
   "channel":{
      "user_logo":"/static/img/channel/test-account_54f988997d191_large.jpg",
      "user_logo_small":"/static/img/channel/test-account_54f988997d191_small.jpg",
      "channel_link":"http://hitbox.tv/test-account"
   }
}
```

The video array will be filled with the [Video Object](https://github.com/Hitakashi/Hitbox-API/blob/master/media/video.md#get-mediavideomedia_id) excluding `media_description` and `media_description_md`

## `POST /team`

Create a team.

### Example URL

https://www.hitbox.tv/api/team?authToken=SuperSecret

### Example POST Payload

`group_display_name` must match `group_name` except in casing.

```javascript
{
   "authToken":"SuperSecret",
   "group_user_name":"test-account",
   "group_name":"TestTeam",
   "group_text":"This is a test team.",
   "group_display_name":"TesTeAm"
}
```

### Example Response

This API actually returns information!

If group is successfully created
```javascript
{
    "success":true,
    "success_msg":"team_created"
}
```

If group name is taken
```javascript
{
    "success":false,
    "error":true,
    "error_msg":"group_taken"
}
```

If `group_display_name` is different than `group_name`
```javascript
{
    "error":true,
    "error_msg":"invalid_display_name"
}
```

If `group_text` is too short or invalid
```javascript
{
    "error":true,
    "error_msg":"text_required"
}
```

If `authToken` is invalid
```javascript
{
    "success":false,
    "error":true,
    "error_msg":"permission_denied"
}
```

## `PUT /team/:teamname/:username`

Updates a team object

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| nocache | No | boolean | Server Side Switch? |
| action | no | string | Valid: delete_team, delete_logo, delete_cover |
| authToken | Yes | string | Founders Auth Token |


### Example URL

https://www.hitbox.tv/api/team/test-team/test-account?authToken=123321

### Example Payload

You must send the object you get from a GET /team/:teamname but can be shorted down:

To upload a team icon you must do a [POST /upload/team/:user/:auth](https://github.com/Hitakashi/Hitbox-API/blob/master/user/upload.md#post-uploadteamusernameauth) which will return logo->small and logo->large which then can be put into `group_logo_small` and `group_logo_large` respectively.

To delete a logo you must set URL param `action` to `delete_logo`

To upload a team cover you must do a [POST /upload/team/:user/:auth](https://github.com/Hitakashi/Hitbox-API/blob/master/user/upload.md#post-uploadteamusernameauth) which will return cover->cover which then can be put into `group_cover`

To delete a cover you must set URL param `action` to `delete_cover`

Deleting a cover or logo will return `group_logo_small`, `group_logo_large` and `group_cover` as "" instead of null like a new team.

To disband a team set `action` to `delete_team` and PUT the required data below.

```javascript
{
   "info":{
      "group_id":"13234",
      "founder_name":"test-admin",
      "group_name":"testapi",
      "group_display_name":"testapi",
      "group_text":"This is a test!",
      "group_logo_large":null,
      "group_logo_small":null,
      "group_cover":null
   },
   "invites": [
    "New-Team-Member"
   ]
}
```

### Example Response

If successful you will get an echo back of the PUT payload

Invalid Payload or Incorrect Auth Token

```javascript
permission_denied
```

## `UPDATE /team/:teamname/:username`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| group_id | Yes | int | Teams group id |

`:teamname` is the team you want to accept the invite.

### Example URL

https://www.hitbox.tv/api/team/test-team/test-account?authToken=SuperSecret&group_id=123

### Example Responses

```javascript
{
    "success":true,
    "success_msg":"accepted_test-account"
}
```

## `DELETE /team/:teamname/:username`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| group_id | Yes | int | Teams group id |

`teamname` is the team you want to kick `username` from. With this API you can kick users from your own team or remove yourself. Providing the Auth Token is correct for yourself (Removing yourself from teams) or correct for the founder of the team (Removing others)

**Note**: Founders that want to leave should disband with [PUT /team/:teamname/:username](/team/team.md#put-teamteamnameusername)

### Example URL

https://www.hitbox.tv/api/team/test-team/test-account?authToken=SuperSecret&group_id=123

### Example Response

```javascript
{
    "success":true,
    "success_msg":"deleted_Hitakashi-Test"
}
```

It also returns a few others like `permission_denied` or `deleted_` providing the auth token or wrong or correct but the user isn't in the team.
