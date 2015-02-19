# Subscription List API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /subscriptionlist/:user](/subscriptionlist.md#get-subscriptionlistuser) | Returns stream stats |

## `GET /subscriptionlist/:user`

Returns channels you have subscribed to.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| nocache | no | string | ? |

### Example URL

https://www.hitbox.tv/api/subscriptionlist/test-account?authToken=12312321312

### Example Response 

If subscriptions are found:

```json
{
  "request":{
    "this":"/subscriptionlist/test-account"
  },
  "subscriptions":[
    {
      "followers":"1",
      "sub_id":"0000",
      "sub_date_added":"2015-02-19 09:59:57",
      "sub_date_valid":"2015-03-19 09:59:58",
      "sub_payment_method":"paypal",
      "canceled":null,
      "plan_charge":"5.00",
      "plan_currency":"USD",
      "plan_recurring":"1",
      "plan_id":"123",
      "user_name":"test-partner",
      "user_id":"133",
      "user_logo":"/static/img/channel/test-partner_54daaee85a902_large.jpg",
      "user_logo_small":"/static/img/channel/test-partner_54daaee85a902_small.jpg",
      "user_cover":"/static/img/channel/cover_54dce1ef89661.jpg",
      "benefits":[
        {
          "name":"Emotes",
          "text":"Exclusive Emoticons",
          "type":"emote",
          "media":null
        }
      ]
    }
  ]
}
```

No Subscriptions:

```json
subscription_not_found
```
