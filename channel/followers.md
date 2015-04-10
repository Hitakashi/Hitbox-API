# Followers API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /followers/user/:channel](/channel/followers.md#get-followersuserchannel) | Returns users that follow a channel. |

## `GET /followers/user/:channel`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| reverse | no | boolean | Reverses the results |
| sort | no | string | Valid: date_added, user_name, user_id, follower_notify |
| limit | no | int | Maximum number of objects to fetch. Default is 100. |
| offset | no | int | The offset for pagination. Default is 0. |

Returns users that follow `:channel`.

### Example URL

https://www.hitbox.tv/api/followers/user/test-account

### Example Response 

```json
{
   "request":{
      "this":"/followers/user/test-account"
   },
   "followers":[
      {
         "followers":"0",
         "user_name":"RandomAccount",
         "user_id":"124",
         "user_logo":"/static/img/channel/randomaccount_549125715fb44_large.png",
         "user_logo_small":"/static/img/channel/randomaccount_549125715fb44_small.png",
         "follow_id":"278723",
         "follower_user_id":"124",
         "follower_notify":"1",
         "date_added":"2014-06-06 08:53:28"
      },
      {
         "followers":"7",
         "user_name":"test-account",
         "user_id":"123",
         "user_logo":"/static/img/channel/Hitakashi_53f4e837eb388_large.png",
         "user_logo_small":"/static/img/channel/Hitakashi_53f4e837eb388_small.png",
         "follow_id":"278723",
         "follower_user_id":"123",
         "follower_notify":"1",
         "date_added":"2015-01-02 01:55:25"
      }
   ],
   "max_results":"2"
}
```