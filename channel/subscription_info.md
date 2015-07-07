# Subscription Information
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /subscription/info/channel/:channel](/channel/subscription_info.md#get-subscriptioninfochannelchannel) | Returns subscription information. |

## `GET /subscription/info/channel/:channel`

Returns subscription information for given channel.

**Note**: If the channel does not have a subscription button this API will return `subscription_not_found`

### Example URL

https://www.hitbox.tv/api/subscription/info/channel/test-account

### Example Response 

```javascript
{
   "request":{
      "this":"/subscription/info/channel/test-account"
   },
   "subscription":{
      "plan":{
         "user_id":"1",
         "group_id":"0",
         "plan_id":"5",
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
         "plan_recurring":"1",
         "plan_g2a":"1",
         "plan_xsolla":"1"
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
      "signature":"RandomString"
   }
}
```
