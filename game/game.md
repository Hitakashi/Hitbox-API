# Game API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /game/:gameID](/game/game.md#get-gamegameid) | Returns game information |
| [GET /game/:game-name](/game/game.md#get-gamegamename) | Returns game information |

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

## `GET /game/:game-name`


| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| seo | Yes | boolean | Always set to true |

### Example URL

https://www.hitbox.tv/api/game/dota-2?seo=true

### Example Response 

```json
{
  "request":{
    "this":"/game/dota-2"
  },
  "category":{
    "category_id":"2",
    "category_name":"Dota 2",
    "category_name_short":null,
    "category_seo_key":"dota-2",
    "category_viewers":"1732",
    "category_media_count":"6",
    "category_channels":null,
    "category_logo_small":null,
    "category_logo_large":"/static/img/games/2433293-1555513-logo610-1.jpg",
    "category_updated":"2015-01-26 01:43:45"
  }
}
```
