# Twitter API
***

| Endpoint | Description |
| ---- | --------------- |
| [POST /twitter/post](/user/twitter/post.md#post-twitterpost) | Sends a Tweet to a Users linked Twitter account. |

## `POST /twitter/post`

Sending a POST request with the data below will send a tweet to twitter.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| user_name | Yes | string | Username |

### Example URL

https://www.hitbox.tv/api/twitter/post?authToken=123&user_name=test-account

### Example POST Payload

```json
{
  "message":"Hello Twitter!"
}
```

### Example Response 

Even if it fails:
```json
success
```
