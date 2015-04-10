# Notification API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /notifications](/user/notifications.md#get-notifications) | Returrns notification settings |
| [PUT /notifications](/user/notifications.md#post-notifications) | Updates notification settings |

## `GET /notifications`

Returns the users notification settings.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| user_name | Yes | string | User's Username |

### Example URL

https://www.hitbox.tv/api/notifications?authToken=SuperSecret&user_name=test-account

### Example Response 

```json
{
   "notify_email":"0",
   "notify_facebook":"0",
   "push_facebook":"0",
   "push_twitter":"0",
   "push_youtube":"0"
}
```

## `PUT /notifications`



| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| user_name | Yes | string | User's Username |

### Example URL

https://www.hitbox.tv/api/notifications?authToken=123&user_name=test-account

### Example POST Payload 

```json
{
   "notify_email":"0",
   "notify_facebook":"0",
   "push_facebook":"0",
   "push_twitter":"0",
   "push_youtube":"0"
}
```
