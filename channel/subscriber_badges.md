# Subscriber Badges
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /mediabadges/:channel](/channel/subscriber_badges.md#get-mediabadgeschannel) | Returns subscriber chat badge. |

## `GET /mediabadges/:channel`

Returns information about subscriber chat badges.
**Note**: If `badge_id` and/or `badge_media_id` doesn't exist they don't have a chat icon.

### Example URL

https://www.hitbox.tv/api/mediabadges/:channel

### Example Response 

If account has a subscribe button.
```javascript
{
   "request":{
      "this":"/mediabadges/test-account"
   },
   "badges":[
      {
         "badge_id":"111",
         "badge_media_id":"123",
         "badge_name":"test-account",
         "badge_image":"/static/img/chat/test-account/badge.png",
         "badge_enabled":"1"
      }
   ]
}
```
