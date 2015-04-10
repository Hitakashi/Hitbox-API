# Hosters API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /hosters/:channel](/channel/hosters.md#get-hosterschannel) | Returns channels hosting your stream. |

## `GET /hosters/:channel`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Get channels that are hosting `:channel`

### Example URL

https://www.hitbox.tv/api/hosters/test-account?authToken=SuperSecert

### Example Response 

Hosters:
```json
{
  "hosters":[
    {
      "user_name":"test-hosters",
      "user_logo":"/static/img/channel/test-hosters_54b7307c3d741_large.png"
    },
    ...
  ]
}
```

No Hosters:
```json
{
  "hosters":[]
}
```
