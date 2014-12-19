# Team API
***

What is the general description of what the endpoint does. You don't have to include parameters if the endpoint doesn't have them.

| Endpoint | Description |
| ---- | --------------- |
| [GET /team/:teamname](/team.md#get-teamteamname) | Get information about teams. |

## `GET /team/:teamname`

Return members and team information.

### Example URL

https://www.hitbox.tv/api/team/:teamname

### Example Response 

```json
{
   "teams":[
      {
         "info":{
            "group_id":"123",
            "founder_name":"Glorious-Leader",
            "group_name":"TheBestTeam",
            "group_display_name":"TheBestTeam",
            "group_text":"We rule. Obviously.",
            "group_logo_small":"\/static\/img\/teams\/logo_52d4870d92afaa_small.jpg",
            "group_logo_large":"\/static\/img\/teams\/logo_52d8704d92afaa_large.jpg",
            "group_cover":"\/static\/img\/teams\/cover_52d870a3e19343.jpg",
         },
         "founder":{
            "user_name":"Glorious-Leader",
            "user_cover":"\/static\/img\/channel\/cover_532ca1307ac13.jpg",
            "user_status":"1",
            "user_logo":"\/static\/img\/channel\/Glorious-Leader_52d334823811d_large.png",
            "user_logo_small":"\/static\/img\/channel\/Glorious-Leader_52d334823811d_small.png",
            "user_is_broadcaster":true,
            "followers":"46",
            "user_partner":null,
            "user_id":"158",
            "is_live":"0",
            "live_since":"2014-09-24 02:32:15",
            "twitter_account":null,
            "twitter_enabled":null
         },
         "members":[
            {
               "user_name":"test-account",
               "user_cover":null,
               "user_status":"1",
               "user_logo":"\/static\/img\/channel\/test-account_53867c57ba993_large.jpg",
               "user_logo_small":"\/static\/img\/channel\/test-account_53867c57ba993_small.jpg",
               "user_is_broadcaster":false,
               "followers":"0",
               "user_partner":null,
               "user_id":"157",
               "is_live":null,
               "live_since":null,
               "twitter_account":null,
               "twitter_enabled":null,
               "group_role":"member",
               "group_accepted":true
            },
            {
               "user_name":"Glorious-Leader",
               "user_cover":"\/static\/img\/channel\/cover_532ca1307ac13.jpg",
               "user_status":"1",
               "user_logo":"\/static\/img\/channel\/Glorious-Leader_52d334823811d_large.png",
               "user_logo_small":"\/static\/img\/channel\/Glorious-Leader_52d334823811d_small.png",
               "user_is_broadcaster":true,
               "followers":"46",
               "user_partner":null,
               "user_id":"158",
               "is_live":"0",
               "live_since":"2014-09-24 02:32:15",
               "twitter_account":null,
               "twitter_enabled":null,
               "group_role":"admin",
               "group_accepted":true
            }
         ]
      }
   ]
}
```

## `POST /team`

Create a team.

## Example URL

https://www.hitbox.tv/api/team

### Example POST Payload

`group_display_name` must match `group_name` except in casing.

```json
{
   "authToken":"1233123123123123",
   "group_user_name":"test-account",
   "group_name":"TestTeam",
   "group_text":"This is a test team.",
   "group_display_name":"TesTeAm"
}
```

### Example Response

This API actually returns information!

If group is successfully created
```json
team_created
```

If group name is taken
```json
group_taken
```

If `group_display_name` is different than `group_name`
```json
invalid_display_name
```

If `group_text` is too short or invalid
```json
text_required
```

If `authToken` is invalid
```json
permission_denied
```
