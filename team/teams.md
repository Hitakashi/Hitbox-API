# Team API
***

What is the general description of what the endpoint does. You don't have to include parameters if the endpoint doesn't have them.

| Endpoint | Description |
| ---- | --------------- |
| [GET /teams](/team/teams.md#get-teams-search) | Searches for teams. |
| [GET /teams/:user](/team/teams.md#get-teamsuser) | Returns teams for provided user. |

## `GET /teams (Search)`

Ability to search for teams by providing a search term. The Website Search feature uses this.

| Parameter | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| search | yes | string | Team title to search for. | 

### Example URL

https://www.hitbox.tv/api/teams

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
            "group_default":0
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
## `GET /teams/:user`

Returns all the teams a user is a member of. Passing a valid authToken replaces the authToken user's blocks with a authenticated [/user/:user](index.md#get-useruser) block.

For example there's a team with "test-account" and "test-account2" and you run /teams/test-account?authToken=test-account2authToken it will replace "test-account2" user blocks with an authenticated user information.

Passing a valid authToken removes the `user_is_broadcaster` token. It also changes `is_live` to `media_is_live`, `live_since` to `media_live_since` and adds `livestream_count`

| Parameter | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | No | string | Users Auth Token. | 
| partner | No | boolean | Only shows teams with sub buttons |

### Example URL

https://www.hitbox.tv/api/teams/test-account

### Example Response 

This example is not using an authToken.
```json
{
   "teams":[
      {
         "info":{
            "group_id":"22222",
            "founder_name":"test-admin",
            "group_name":"TheBestTeam",
            "group_display_name":"The_Best_Team",
            "group_text":"Test Team for working with the Hitbox API.",
            "group_logo_small":null,
            "group_logo_large":null,
            "group_cover":null,
            "group_role":"member",
            "group_accepted":true,
            "group_default":0
         },
         "founder":{
            "user_name":"test-admin",
            "user_cover":"\/static\/img\/channel\/cover_53fbf0653372c78.png",
            "user_status":"1",
            "user_logo":"\/static\/img\/channel\/test-admin_53f4e837eb388_large.png",
            "user_logo_small":"\/static\/img\/channel\/test-admin_53f4e837eb388_small.png",
            "user_is_broadcaster":true,
            "followers":"7",
            "user_partner":null,
            "user_id":"342",
            "is_live":"0",
            "live_since":"2014-12-14 05:18:54",
            "twitter_account":"test-admin",
            "twitter_enabled":"0"
         },
         "members":[
            {
               "user_name":"test-admin",
               "user_cover":"\/static\/img\/channel\/cover_53fbf0653372c78.png",
               "user_status":"1",
               "user_logo":"\/static\/img\/channel\/test-admin_53f4e837eb388_large.png",
               "user_logo_small":"\/static\/img\/channel\/test-admin_53f4e837eb388_small.png",
               "user_is_broadcaster":true,
               "followers":"7",
               "user_partner":null,
               "user_id":"342",
               "is_live":"0",
               "live_since":"2014-12-14 05:18:54",
               "twitter_account":"test-admin",
               "twitter_enabled":"0",
               "group_role":"admin",
               "group_accepted":true
            },
            {
               "user_name":"test-member",
               "user_cover":"\/static\/img\/channel\/cover_53aa863200ade74.png",
               "user_status":"1",
               "user_logo":"\/static\/img\/channel\/test-member_549125715fb44_large.png",
               "user_logo_small":"\/static\/img\/channel\/test-member_549125715fb44_small.png",
               "user_is_broadcaster":true,
               "followers":"0",
               "user_partner":null,
               "user_id":"232",
               "is_live":"0",
               "live_since":null,
               "twitter_account":"test-twitter2",
               "twitter_enabled":"0",
               "group_role":"member",
               "group_accepted":true
            }
         ]
      }
   ]
}
```
