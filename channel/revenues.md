# Revenues Stats API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /revenues/channel/:user](/channel/revenues.md#get-revenueschanneluser) | Returns Revenues stats |

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
      "max_earnings":null
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
