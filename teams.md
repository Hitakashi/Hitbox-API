# Team API
***

What is the general description of what the endpoint does. You don't have to include parameters if the endpoint doesn't have them.

| Endpoint | Description |
| ---- | --------------- |
| [GET /teams](/teams.md#get-teams-search) | Searches for teams. |

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
