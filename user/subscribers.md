# Subscriber API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /subscriptionlist/:user](/user/subscribers.md#get-subscriptionlistuser) | Returns Subscriptions List |
| [GET /subscriberlist/:user](/user/subscribers.md#get-subscriberlistuser) | Returns Subscribers List |

## `GET /subscriptionlist/:user`

Returns channels you have subscribed to.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

### Example URL

https://www.hitbox.tv/api/subscriptionlist/test-account?authToken=SuperSecret

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

## `GET /subscriberlist/:user`

Returns users that have subscribed to `:user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

**Note**: Always check `sub_date_valid` as `canceled` can be incorrect. (Canceling outside of the website)

Will return `no_subscribers_found` if you have no subscribers.

##$ Example URL 

https://www.hitbox.tv/api/subscriberlist/test-account?authToken=SuperSecret

### Example Response

```json
{
   "request":{
      "this":"/subscriberlist/test-account"
   },
   "subscribers":[
      {
         "followers":"123",
         "user_name":"Masta",
         "user_id":"1",
         "user_logo":"/static/img/channel/masta_55270735d51ac_large.jpg",
         "user_logo_small":"/static/img/channel/masta_55270735d51ac_small.jpg",
         "sub_date_added":"2015-01-20 15:49:51",
         "sub_date_valid":"2015-07-20 04:35:31",
         "sub_payment_method":"paypal",
         "canceled":null
      }
   ]
}
```