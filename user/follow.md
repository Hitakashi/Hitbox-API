# Follow API
***


| Endpoint | Description |
| ---- | --------------- |
| [POST /follow](/user/follow.md#post-follow) | Follows a user |
| [DELETE /follow](/user/follow.md#delete-follow) | Unfollows a user |

## `POST /follow`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Follows a user via their user id (`follow_id`)

### Example URL

https://www.hitbox.tv/api/follow?authToken=SuperSecret

### Example POST Payload 

```json
{
   "type":"user",
   "follow_id":"278723"
}
```

### Example Response

```json
following
```

## `DELETE /follow`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| follow_id | Yes | string | User's ID |
| type | Yes | string | Unknown, Default: user |

Unfollows a user via their user id (`follow_id`)

### Example URL

https://www.hitbox.tv/api/follow?authToken=SuperSecret&follow_id=278723&type=user

### Example Response 

```json
un-followed
```
