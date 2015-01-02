# Following API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /following/user](/following.md#get-followinguser) | Returns a list of channels a user is following. |

## `GET /following/user`

Returns a list of channels a user is following.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| nocache | No | boolean | Server Side Switch? |
| sort | No | string | Valid Sort: date_added, user_name, follow_id,user_id, follower_notify |
| user_name | Yes | string | User's user name |
| offset | no | int | offsets the results by the given amount |
| limit | no | int | Limits the results |

### Example URL

https://www.hitbox.tv/api/following/user?user_name=test-account

### Example Response 

```json
{
   "request":{
      "this":"\/following\/user"
   },
   "following":[
      {
         "followers":"41",
         "user_name":"test-account",
         "user_id":"123",
         "user_logo":"\/static\/img\/channel\/test-account_54731f215b60c_large.jpg",
         "user_logo_small":"\/static\/img\/channel\/test-account_54731f215b60c_small.jpg",
         "follow_id":"123",
         "follower_user_id":"278723",
         "follower_notify":"1",
         "date_added":"2014-07-04 02:35:48"
      },
      {
         "followers":"7",
         "user_name":"RandomDude",
         "user_id":"124",
         "user_logo":"\/static\/img\/channel\/RandomDude_53f4e837eb388_large.png",
         "user_logo_small":"\/static\/img\/channel\/RandomDude_53f4e837eb388_small.png",
         "follow_id":"124",
         "follower_user_id":"278723",
         "follower_notify":"1",
         "date_added":"2015-01-02 01:55:25"
      }
   ],
   "max_results":"2"
}
```
