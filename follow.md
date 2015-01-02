# Follow API
***


| Endpoint | Description |
| ---- | --------------- |
| [POST /follow](/follow.md#post-follow) | Follows a user |
| [DELETE /follow](/follow.md#delete-follow) | Unfollows a user |

## `POST /follow`

Follows a user via their user id

### Example URL

https://www.hitbox.tv/api/follow?authToken=123213213213

### Example POST Payload 

```json
{
   "type":"user",
   "follow_id":"278723",
   "authToken":"12321312312321"
}
```

### Example Response

```json
following
```

## `DELETE /follow`

Unfollows a user via their user id

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| follow_id | Yes | string | User's ID |
| type | Yes | string | Unknown, Default: user |

### Example URL

https://www.hitbox.tv/api/follow?authToken=1321321&follow_id=278723&type=user

### Example Response 

```json
un-followed
```
