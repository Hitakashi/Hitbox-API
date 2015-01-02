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

Sorry, but I have no clue. I don't subscribe to channels.

No Subscriptions:

```json
subscription_not_found
```
