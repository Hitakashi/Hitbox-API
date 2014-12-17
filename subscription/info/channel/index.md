# Subscription Information
***

| Endpoint | Description |
| ---- | --------------- |
| [POST /subscription/info/channel/:channel](/subscription/info/channel/index.md#get-subscriptioninfochannelchannel) | Returns subscription information. |

## `GET /subscription/info/channel/:channel`

Returns subscription information for given channel.

### Example URL

https://www.hitbox.tv/api/subscription/info/channel/test-account

### Example Payload 

```json
{
   "request":{
      "this":"\/subscription\/info\/channel\/theebstream"
   },
   "subscription":{
      "plan":{
         "user_id":"111",
         "group_id":"0",
         "plan_id":"123",
         "date_added":"2014-07-22 12:15:24",
         "plan_group_id":null,
         "plan_name":"test-account",
         "plan_prefix":"ta",
         "plan_charge":"4.99",
         "plan_share":"0.50",
         "plan_currency":"USD",
         "plan_ads":"0",
         "plan_hd":"0",
         "plan_videos":"0",
         "plan_recurring":"1"
      },
      "benefits":[
         {
            "name":"Support Broadcaster",
            "text":"Support the broadcaster",
            "type":"none"
         },
         {
            "name":"Badge",
            "text":"Subscriber Badge",
            "type":"badge"
         },
         {
            "name":"Emotes",
            "text":"Exclusive Emoticons",
            "type":"emote"
         }
      ]
   },
   "recurly":{
      "signature":"randomsignature|nonce=randomnumbers&subscription%5Bplan_code%5D=11&subscription%5Bcurrency%5D=USD×tamp=randomnumber"
   }
}
```
