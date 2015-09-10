# Revenues Stats API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /revenues/channel/:user](/channel/revenues.md#get-revenueschanneluser) | Returns Revenues stats |
| [GET /payments/balance/:user](/channel/revenues.md#get-paymentsbalanceuser) | Get Payment Balance |
| [GET /transactions/history/:user](/channel/revenues.md#get-transactionshistoryuser) | Get Transaction History |
| [GET /payments/settings/:user](/channel/revenues.md#get-paymentssettingsuser) | Get Payment Settings |

## `GET /revenues/channel/:user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| endDate | Yes | Date | Date in YYYY-MM-DD |
| startDate | Yes | Date | Date in YYYY-MM-DD |

Returns revenues for given channel between `startDate` and `endDate`.

I have truncated each array to just one property.

### Example URL

https://www.hitbox.tv/api/revenues/channel/test-account?authToken=SuperSecret&endDate=2015-04-08&startDate=2015-03-07

### Example Response 

Non-Parter Info: (I assume Partners follow the same layout)
```javascript
{
   "request":{
      "this":"/revenues/channel/test-account",
      "type":"channel",
      "user":"test-account"
   },
   "revenues":{
      "summary":{
         "currency":"EUR",
         "total_earnings":0,
         "max_earnings":null,
         "viewed_hours":0,
         "unique_user":0
      },
      "plans":[

      ],
      "timeline":[
         [
            1427673600000,
            0
         ]
      ],
      "daily":{
         "2015-03-30":{
            "earnings":0
         }
      },
      "groups":{
         "1425686400000":[
            null,
            null
         ]
      },
      "live":{
         "1425686400000":null
      },
      "total":{
         "1425686400000":null
      },
      "timeline_ads":[
         [
            1425686400000,
            null
         ]
      ],
      "timeline_subs":[
         [
            1425686400000,
            null
         ]
      ],
      "subs":{
         "1425686400000":null
      },
      "top":{
         "countries":[

         ],
         "content":{
            "live":{
               "earnings":0
            },
            "video":{
               "earnings":0
            },
            "subscriptions":{
               "earnings":0
            }
         }
      }
   }
}
```

## `GET /payments/balance/:user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns balance for `user`. Broadcaster Only.

### Example URL

https://www.hitbox.tv/api/payments/balance/test-account?authToken=SuperSecret

### Example Response

```javascript
[
    {
        "user_id":"1",
        "plan_currency":"EUR",
        "minDate":"2015-08",
        "maxDate":"2015-09",
        "sub_earnings":"0.00",
        "live_earnings":"0.00",
        "video_earnings":"0.00",
        "min_threshold":"0.00",
        "special_credits":"0.00"
    }
]
```

## `GET /transactions/history/:user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns transaction history for `user`. Broadcaster Only.

### Example URL

https://www.hitbox.tv/api/transaction/history/test-account?authToken=SuperSecret

### Example Response

```javascript
{
    "request":{
        "this":"/transactions/history/test-account",
        "user":"test-account"
    },
    "orders":[
        {
            "breakdown":[
                {
                    "payorder_id":"1",
                    "currency":"EUR",
                    "month_disp":"2015-07",
                    "credit_date":"2015-07-31",
                    "reason":"Revenue share",
                    "amount":"0.00"
                }
            ],
            "order_id":0,
            "status":"Verified",
            "order_date":null,
            "period_start":"2015-04-01",
            "period_end":"2015-07-31",
            "order_amount":"0.00",
            "order_ccy":"EUR",
            "order_error":null,
            "publicorderident":"00000-000000-000000-0",
            "pay_date":"2015-01-1"
        }
    ]
}
```

## `GET /payments/settings/:user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns payment settings for `user`. Information is always blanked out by hitbox as '*****'. Broadcaster Only.

### Example URL

https://www.hitbox.tv/api/payments/settings/test-account?authToken=SuperSecret

### Example Response

```javascript
{
    "user_name":"test-account",
    "user_partner":"4",
    "group_partner":"0",
    "team_name":"bestteam",
    "emailverified":"1",
    "partner_type":"migrated",
    "settings_status":"Missing payment details",
    "user_id":"1",
    "date_added":"",
    "country":"",
    "currency":"",
    "paypal_recipient":"****",
    "bank_IBAN":"****",
    "bank_SWIFT":"****",
    "first_name":"****",
    "last_name":"****",
    "legal_name":"****",
    "address1":"****",
    "address2":"****",
    "address3":"****",
    "address4":"****",
    "mobile":"****",
    "postcode":"****",
    "city":"****",
    "region":"****",
    "birthDay":"",
    "birthMonth":"",
    "birthYear":"",
    "birth_date":"****",
    "tax_code":"****",
    "vat_code":"****"
}
```