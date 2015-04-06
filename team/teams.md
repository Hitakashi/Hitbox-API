# Team API
***

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
         "members":[
            {
               "followers":"0",
               "user_id":"157",
               "user_name":"test-account",
               "user_status":"1",
               "user_logo":"\/static\/img\/channel\/test-account_53867c57ba993_large.jpg",               
               "user_cover":null,
               "user_logo_small":"\/static\/img\/channel\/test-account_53867c57ba993_small.jpg",
               "user_partner":null,
               "admin": null,
               "enabled": "1",
               "group_role":"member",
               "group_accepted":true
            },
            {
               "followers":"46",
               "user_id":"158",
               "user_name":"Glorious-Leader",
               "user_status":"1",
               "user_logo":"\/static\/img\/channel\/Glorious-Leader_52d334823811d_large.png",
               "user_cover":"\/static\/img\/channel\/cover_532ca1307ac13.jpg",
               "user_logo_small":"\/static\/img\/channel\/Glorious-Leader_52d334823811d_small.png",
               "user_partner":null,
               "admin": "1",
               "enabled": "1",
               "group_role":"admin",
               "group_accepted":true
            }
         ]
      }
   ]
}
```
## `GET /teams/:user`

Returns a list of team objects for `:user`

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
         "members":[
            {
               "followers":"46",
               "user_id":"158",
               "user_name":"Glorious-Leader",
               "user_status":"1",
               "user_logo":"\/static\/img\/channel\/Glorious-Leader_52d334823811d_large.png",
               "user_cover":"\/static\/img\/channel\/cover_532ca1307ac13.jpg",
               "user_logo_small":"\/static\/img\/channel\/Glorious-Leader_52d334823811d_small.png",
               "user_partner":null,
               "admin": "1",
               "enabled": "1",
               "group_role":"admin",
               "group_accepted":true
            },
            {
               "followers":"0",
               "user_id":"157",
               "user_name":"test-account",
               "user_status":"1",
               "user_logo":"\/static\/img\/channel\/test-account_53867c57ba993_large.jpg",               
               "user_cover":null,
               "user_logo_small":"\/static\/img\/channel\/test-account_53867c57ba993_small.jpg",
               "user_partner":null,
               "admin": null,
               "enabled": "1",
               "group_role":"member",
               "group_accepted":true
            }
         ]
      }
   ]
}
```
