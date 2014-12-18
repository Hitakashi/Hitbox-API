# Games API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /games](/games.md#get-games) | Return games |
| [GET /games/top](/games.md#get-gamestop) | Return top games by viewers |

## `GET /games`

Returns games. 

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| q | No | string | Query to search for. |
| limit | No | int | Number of games to limit. Default 100 |

### Example URL

https://www.hitbox.tv/api/games

### Example Response 

```json
{
   "request":{
      "this":"\/games"
   },
   "categories":[
      {
         "category_id":"457",
         "category_name":"Team Fortress 2",
         "category_name_short":null,
         "category_seo_key":"team-fortress-2",
         "category_viewers":"1",
         "category_media_count":"1",
         "category_channels":null,
         "category_logo_small":null,
         "category_logo_large":"\/static\/img\/games\/team_fortress_2.jpg",
         "category_updated":"2014-12-17 19:42:24"
      },
      {
         "category_id":"4900",
         "category_name":"Team Fortress Classic",
         "category_name_short":null,
         "category_seo_key":"team-fortress-classic",
         "category_viewers":"0",
         "category_media_count":"1",
         "category_channels":null,
         "category_logo_small":null,
         "category_logo_large":"\/static\/img\/games\/1047035-team_fortress_classic_box.jpg",
         "category_updated":"2014-11-29 04:08:15"
      },
      {
         "category_id":"11039",
         "category_name":"Team Factor",
         "category_name_short":null,
         "category_seo_key":"team-factor",
         "category_viewers":null,
         "category_media_count":null,
         "category_channels":null,
         "category_logo_small":null,
         "category_logo_large":"\/static\/img\/generic\/blank.gif",
         "category_updated":"2014-05-05 13:51:37"
      }
   ]
}
```


## `GET /games/top`

Return top games by viewers. 

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| q | No | string | Restrict by game name or a search of. |
| limit | No | int | Number of games to limit to. |

### Example URL

https://www.hitbox.tv/api/games/top?limit=1

### Example Response

```json
{
   "request":{
      "this":"\/games\/top"
   },
   "categories":[
      {
         "category_id":"27295",
         "category_name":"Magical Drop V",
         "category_name_short":null,
         "category_seo_key":"magical-drop-v",
         "category_viewers":"2980",
         "category_media_count":"1",
         "category_channels":null,
         "category_logo_small":null,
         "category_logo_large":"\/static\/img\/games\/1837871-632845_213931_front.jpg",
         "category_updated":"2014-11-16 14:09:08"
      }
   ]
}
```
