# Game API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /game/:gameID](/game/index.md#get-gamegameid) | Returns game information |

## `GET /game/:gameID`

Returns game information.

### Example URL

https://www.hitbox.tv/api/game/30686

### Example Response 

```json
{
   "request":{
      "this":"\/game\/30686"
   },
   "category":{
      "category_id":"30686",
      "category_name":"Elite: Dangerous",
      "category_name_short":null,
      "category_seo_key":"elite-dangerous",
      "category_viewers":"361",
      "category_media_count":"8",
      "category_channels":null,
      "category_logo_small":null,
      "category_logo_large":"\/static\/img\/games\/elite-dangerous.png",
      "category_updated":"2014-12-18 02:10:24"
   }
}
```
