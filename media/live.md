# Live API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /media/live/:channel](/media/live.md#get-medialivechannel) | Returns live stream information. |
| [GET /media/live/list](/media/live.md#get-medialivelist) | Returns channels |
| [PUT /media/live/:channel](/media/live.md#put-medialivechannel) | Updates live stream information. |
| [POST /media/live/:channel](/media/live.md#post-medialivechannel) | Create stream on new account |

## `GET /media/live/:channel`

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | No | string | Users Auth Token. Used if wanting private user information. | 
| showHidden | Sorta | boolean | Show Hidden Streams. |

Returns stream information. You can only get this information if the user has setup their livestream.

I recommend only using `showHidden` when you have 'permission' for example they join your bot to their channel.

Hosting a channel:
If a channel is being hosted they add a these:

`media_hosted_id`: Media ID of hosted channel.

`media_hosted_media`: Literally shoving this same API of hosted user into this javascript object.

### Example URL

https://www.hitbox.tv/api/media/live/test-account

### Example Response

If valid authToken is passed and host is off
```javascript
{
   "request":{
      "this":"/media/live/test-account"
   },
   "media_type":"live",
   "authToken":"SuperSecret",
   "livestream":[
      {
         "media_user_name":"test-account",
         "media_id":"13830",
         "media_type_id":"1",
         "media_user_id":"278123",
         "media_category_id":"304386",
         "media_file":"test-account",
         "media_profiles":null,
         "media_host":"x.x.x.x",
         "media_rec_session":"b33e94023fe4973416d8d815addd290e07d50624",
         "media_repair_source": null,
         "media_ingest_host":null,
         "media_is_live":"0",
         "media_live_delay":null,
         "media_featured":null,
         "media_privacy":null,
         "media_hidden":"1",
         "media_notify_users":"1",
         "media_date_added":"2014-01-07 06:38:01",
         "media_date_updated":"2014-12-14 05:19:21",
         "media_live_since":"2014-12-14 05:18:54",
         "media_live_notified":"2014-11-10 21:03:06",
         "media_mature":null,
         "media_key":"DaKongHasIt",
         "media_chat_enabled":"1",
         "media_deleted":null,
         "media_playing":"1",
         "media_transcoding":null,
         "media_uploaded": null,
         "media_recording":"1",
         "media_dvr":"0",
         "media_countries":[
            "US"
         ],
         "media_info":null,
         "media_relay":"",
         "media_password_protected":null,
         "media_yt_upload":null,
         "media_yt_upload_status":null,
         "media_processing":null,
         "media_total_views":"1",
         "media_monthly_views":null,
         "media_weekly_views":null,
         "media_daily_views":null,
         "media_hosted_id":null,
         "media_mature":null,
         "media_featured_weight":null,
         "media_featured_forced":null,
         "media_featured_countries":null,
         "media_name":"test-account",
         "media_offline_id":null,
         "media_display_name":"test-account",
         "media_status":"LiveStream Title",
         "media_title":"",
         "media_description":"Stream Profile without markdown",
         "media_description_md":"<p>Stream Profile in Markdown<\/p>\n",
         "media_tags":"",
         "media_duration":"0.0000",
         "media_bg_image":"/static/img/channel/cover_53f21bf06572c78.png",
         "media_views":"0",
         "media_views_daily":"0",
         "media_views_weekly":"0",
         "media_views_monthly":"0",
         "category_id":"30686",
         "category_name":"Elite: Dangerous",
         "category_name_short":null,
         "category_seo_key":"elite-dangerous",
         "category_viewers":"405",
         "category_media_count":"9",
         "category_channels":null,
         "category_logo_small":null,
         "category_logo_large":"/static/img/games/elite-dangerous.png",
         "category_updated":"2014-12-18 00:42:25",
         "team_name":"TheBestTeam",
         "user_banned":null,
         "media_start_in_sec":"0",
         "media_download_link":"http://edge.bf.hitbox.tv/download/?h=wkq9jK_GLOyY222213orqw&e=1418867029",
         "media_duration_format":"00:00:00",
         "media_thumbnail":"/static/img/media/live/test-account_mid_000.jpg",
         "media_thumbnail_large":"/static/img/media/live/test-account_large_000.jpg",
         "channel":{
            "followers":"7",
            "user_id":"1321312",
            "user_name":"test-account",
            "user_status":"1",
            "user_logo":"/static/img/channel/test-account_53f4e837eb388_large.png",
            "user_cover":"/static/img/channel/cover_53fbf01572c78.png",
            "user_logo_small":"/static/img/channel/test-account_53f4e837eb388_small.png",
            "user_partner":null,
            "user_beta_profile": "1",
            "media_is_live":"0",
            "media_live_since":"2014-12-14 05:18:54",
            "twitter_account":"test-account",
            "twitter_enabled":"0",
            "livestream_count":"1",
            "user_media_id":"12",
            "channel_link":"http://hitbox.tv/test-account"
         }
      }
   ]
}
```

else

```javascript
{
   "request":{
      "this":"/media/live/test-account"
   },
   "media_type":"live",
   "livestream":[
      {
         "media_user_name":"test-account",
         "media_id":"15820",
         "media_file":"test-account",
         "media_hidden":null,
         "media_user_id":"278123",
         "media_profiles":null,
         "media_type_id":"1",
         "media_is_live":"0",
         "media_live_delay":null,
         "media_date_added":"2014-01-07 06:38:01",
         "media_live_since":"2014-12-14 05:18:54",
         "media_mature":null,
         "media_transcoding":null,
         "media_chat_enabled":"1",
         "media_countries":[
            "US"
         ],
         "media_hosted_id":null,
         "user_banned":null,
         "media_name":"test-account",
         "media_display_name":"test-account",
         "media_status":"Stream Title",
         "media_title":"",
         "media_description":"Stream Profile without markdown",
         "media_description_md":"<p>Stream Profile in Markdown</p>\n",
         "media_tags":"",
         "media_duration":"0.0000",
         "media_bg_image":"/static/img/channel/cover_53fb21572c78.png",
         "media_views":"0",
         "media_views_daily":"0",
         "media_views_weekly":"0",
         "media_views_monthly":"0",
         "category_id":"30686",
         "category_name":"Elite: Dangerous",
         "category_name_short":null,
         "category_seo_key":"elite-dangerous",
         "category_viewers":"401",
         "category_media_count":"10",
         "category_channels":null,
         "category_logo_small":null,
         "category_logo_large":"/static/img/games/elite-dangerous.png",
         "category_updated":"2014-12-18 01:04:25",
         "team_name":"TheBestTeam",
         "media_start_in_sec":"0",
         "media_duration_format":"00:00:00",
         "media_thumbnail":"/static/img/media/live/test-account_mid_000.jpg",
         "media_thumbnail_large":"/static/img/media/live/test-account_large_000.jpg",
         "channel":{
            "followers":"7",
            "user_id":"278123",
            "user_name":"test-account",
            "user_status":"1",
            "user_logo":"/static/img/channel/test-account_53f4e837eb388_large.png",
            "user_cover":"/static/img/channel/cover_53fbf06572c78.png",
            "user_logo_small":"/static/img/channel/test-account_53f4e837eb388_small.png",
            "user_partner":null,
            "user_beta_profile": "1",
            "media_is_live":"0",
            "media_live_since":"2014-12-14 05:18:54",
            "user_media_id":"12",
            "twitter_account":"test-account",
            "twitter_enabled":"0",
            "livestream_count":"1",
            "channel_link":"http://hitbox.tv/test-account"
         }
      }
   ]
}
```

### Errors

```javascript
{
   "success":false,
   "error":true,
   "error_msg":"no_media_found"
}
```

## `GET /media/live/list`

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | No | string | Users Auth Token. Used if wanting private user information. | 
| publicOnly | No | boolean | Show only visible streams. |
| showHidden | Sorta | boolean | Show Hidden Streams. |
| liveonly | No | boolean | Show non-live media objects. |
| filter | No | string | Valid: recent, popular (default). |
| game | No | string | Sorts Media Objects by category id, Game SEO or URL Encoded game name. |
| limit | No | int | Maximum number of objects to fetch. Default and Max. is 100. |
| follow_id | No | String | Shows only live streams that `follow_id` (user ID) follows. |

Returns a list of media objects. 

### Example URL

https://www.hitbox.tv/api/media/live/list

### Example Response

```javascript
{
  "request":{
    "this":"/media/live/list"
  },
  "media_type":"live",
  "livestream":[
    {
      "media_user_name":"Yuuhi",
      "media_id":"109219",
      "media_file":"Yuuhi",
      "media_hidden":null,
      "media_user_id":"415015",
      "media_profiles":"[{\"height\":\"360\",\"bitrate\":\"500\"},{\"height\":\"480\",\"bitrate\":\"1000\"},{\"height\":\"720\",\"bitrate\":\"2000\"}]",
      "media_type_id":"1",
      "media_is_live":"1",
      "media_live_delay":"0",
      "media_date_added":"2014-03-10 00:22:31",
      "media_live_since":"2015-01-23 14:55:29",
      "media_transcoding":"1",
      "media_chat_enabled":"1",
      "media_countries":[
        "PL",
        "GB"
      ],
      "media_hosted_id":null,
      "media_mature":null,
      "user_banned":null,
      "media_name":"yuuhi",
      "media_offline_id":null,
      "media_display_name":"Yuuhi",
      "media_status":"TLoU Remastered - przechodzim fabule :D - Codzienna dawka Gier.",
      "media_title":"",
      "media_tags":"",
      "media_duration":"0.0000",
      "media_bg_image":"/static/img/channel/cover_5495978d7a326.jpg",
      "media_views":"748",
      "media_views_daily":"0",
      "media_views_weekly":"0",
      "media_views_monthly":"0",
      "category_id":"627",
      "category_name":"The Last of Us",
      "category_name_short":null,
      "category_seo_key":"the-last-of-us",
      "category_viewers":"345",
      "category_media_count":"1",
      "category_channels":null,
      "category_logo_small":null,
      "category_logo_large":"/static/img/games/2419553-397060_386577108098888_427807760_n.jpg",
      "category_updated":"2015-01-21 23:11:42",
      "team_name":"jarockpl",
      "media_start_in_sec":"0",
      "media_duration_format":"00:00:00",
      "media_thumbnail":"/static/img/media/live/yuuhi_mid_000.jpg",
      "media_thumbnail_large":"/static/img/media/live/yuuhi_large_000.jpg",
      "channel":{
        "followers":"10371",
        "user_id":"415015",
        "user_name":"Yuuhi",
        "user_status":"1",
        "user_logo":"/static/img/channel/Yuuhi_549599f97d8d0_large.jpg",
        "user_cover":"/static/img/channel/cover_5495978d7a326.jpg",
        "user_logo_small":"/static/img/channel/Yuuhi_549599f97d8d0_small.jpg",
        "user_partner":"1",
        "user_beta_profile": "0",
        "media_is_live":"1",
        "media_live_since":"2015-01-23 14:55:29",
        "twitter_account":null,
        "twitter_enabled":null,
        "livestream_count":"1",
        "user_media_id":"109219",
        "channel_link":"http://hitbox.tv/yuuhi"
      }
    },
    ...
  ]
}
```

### Errors

```javascript
{
   "success":false,
   "error":true,
   "error_msg":"no_media_found"
}
```

## `PUT /media/live/:channel`

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | Users Auth Token. | 

Allows you to update multiple values of the stream, including descriptions. 


### Example URL

https://www.hitbox.tv/api/media/live/test-account?authToken=SuperSecret

### Example PUT Payload
<a name="hostmode"></a>
Setting `media_hosted_name` to a valid hitbox username enables host mode, setting it to "off" disables it.

**Caution**: To correctly update this API, You must send all values below except media_hosted_name and media_description, which is optional unless you want to update the hosted channel or channel description.

```javascript
{
   "livestream":[
      {
         "media_user_name":"test-account",
         "media_id":"15830",
         "media_category_id":"455",
         "media_live_delay":"0",
         "media_hidden":"0",
         "media_recording":"1",
         "media_mature":"1",
         "media_hosted_name": "test-host",
         "media_countries":[
            "US"
         ],
         "media_status":"This is a stream title!",
         "media_description":"This is your profile description!"
      }
   ]
}
```

### Example Response

Enable Host Mode:
```javascript
{
   "success":true,
   "error":false,
   "message":"host_mode_enabled"
}
```
Disable Host Mode:
```javascript
{
   "success":true,
   "error":false,
   "message":"host_mode_disabled"
}
```

```javascript
{
   "livestream":[
      {
         "media_user_name":"test-account",
         "media_id":"15830",
         "media_category_id":"455",
         "media_live_delay":"0",
         "media_hidden":true,
         "media_recording":"1",
         "media_countries":[
            "US"
         ],
         "media_password":false,
         "media_status":"This is a title.9",
         "media_description":"222",
         "media_description_md":"<p>222<\/p>\n"
      }
   ]
}
```

## `POST /media/live/:channel`

| Paramater | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's auth token |

### Example URL

https://www.hitbox.tv/media/live/test-account?authToken=SuperSecret

### Example POST Payload

```javascript
{
   "user_name":"test-account",
   "authToken":"132123",
   "media_type":"live",
   "media_description":"",
   "media_status":"My first hitbox Livestream",
   "media_name":"test-account",
   "media_category_id":""
}
```

### Example Response

```javascript
media_created
```
