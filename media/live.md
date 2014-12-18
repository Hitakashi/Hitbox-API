# Live API
***

This API contains endpoints that describes the provided auth token.

| Endpoint | Description |
| ---- | --------------- |
| [GET /media/live/:channel](/media/live.md#get-useruser) | Get user account information. |

## `GET /media/live/:channel`

Returns stream information. You can only get this information if the user has setup their livestream.

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | No | string | Users Auth Token. Used if wanting private user information. | 
| nocache | No | boolean | No clue. Server side switch probably. |
| filter | No | string | ? |
| hiddenOnly | No | string | ? |
| limit | No | int | ? |
| liveonly | No | boolean | ? |
| publicOnly | No | boolean | ? |
| showHidden | Sorta | boolean | This will return channel information even if the stream is offline. I would always set to true |
| yt | No | boolean | ? |

### Example URL

https://www.hitbox.tv/api/media/live/test-account

### Example Response

If valid authToken is passed
```json
{
   "request":{
      "this":"\/media\/live\/test-account"
   },
   "media_type":"live",
   "authToken":"DaKongInChat",
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
         "media_key":"DaKongHasIt",
         "media_chat_enabled":"1",
         "media_deleted":null,
         "media_playing":"1",
         "media_transcoding":null,
         "media_recording":"1",
         "media_dvr":"0",
         "media_countries":[
            "US"
         ],
         "media_info":null,
         "media_relay":"",
         "media_password":null,
         "media_yt_upload":null,
         "media_yt_upload_status":null,
         "media_processing":null,
         "media_total_views":"1",
         "media_monthly_views":null,
         "media_weekly_views":null,
         "media_daily_views":null,
         "media_featured_weight":null,
         "media_featured_forced":null,
         "media_featured_countries":null,
         "media_name":"hitakashi",
         "media_display_name":"Hitakashi",
         "media_status":"LiveStream Title",
         "media_title":"",
         "media_description":"Stream Profile without markdown",
         "media_description_md":"<p>Stream Profile in Markdown<\/p>\n",
         "media_tags":"",
         "media_duration":"0.0000",
         "media_bg_image":"\/static\/img\/channel\/cover_53f21bf06572c78.png",
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
         "category_logo_large":"\/static\/img\/games\/elite-dangerous.png",
         "category_updated":"2014-12-18 00:42:25",
         "team_name":"TheBestTeam",
         "media_start_in_sec":"0",
         "media_download_link":"http:\/\/edge.bf.hitbox.tv\/download\/?h=wkq9jK_GLOyY222213orqw&e=1418867029",
         "media_duration_format":"00:00:00",
         "media_thumbnail":"\/static\/img\/media\/live\/test-account_mid_000.jpg",
         "media_thumbnail_large":"\/static\/img\/media\/live\/test-account_large_000.jpg",
         "channel":{
            "followers":"7",
            "user_id":"278723",
            "user_name":"Hitakashi",
            "user_status":"1",
            "user_logo":"\/static\/img\/channel\/test-account_53f4e837eb388_large.png",
            "user_cover":"\/static\/img\/channel\/cover_53fbf01572c78.png",
            "user_logo_small":"\/static\/img\/channel\/test-account_53f4e837eb388_small.png",
            "user_partner":null,
            "media_is_live":"0",
            "media_live_since":"2014-12-14 05:18:54",
            "twitter_account":"test-account",
            "twitter_enabled":"0",
            "livestream_count":"1",
            "channel_link":"http:\/\/hitbox.tv\/test-account"
         }
      }
   ]
}
```

else

```json
{
   "request":{
      "this":"\/media\/live\/test-account"
   },
   "media_type":"live",
   "livestream":[
      {
         "media_user_name":"test-account",
         "media_id":"15820",
         "media_file":"test-account",
         "media_user_id":"278123",
         "media_profiles":null,
         "media_type_id":"1",
         "media_is_live":"0",
         "media_live_delay":null,
         "media_date_added":"2014-01-07 06:38:01",
         "media_live_since":"2014-12-14 05:18:54",
         "media_transcoding":null,
         "media_chat_enabled":"1",
         "media_countries":[
            "US"
         ],
         "user_banned":null,
         "media_name":"test-account",
         "media_display_name":"test-account",
         "media_status":"Stream Title",
         "media_title":"",
         "media_description":"Stream Profile without markdown",
         "media_description_md":"<p>Stream Profile in Markdown<\/p>\n",
         "media_tags":"",
         "media_duration":"0.0000",
         "media_bg_image":"\/static\/img\/channel\/cover_53fb21572c78.png",
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
         "category_logo_large":"\/static\/img\/games\/elite-dangerous.png",
         "category_updated":"2014-12-18 01:04:25",
         "team_name":"TheBestTeam",
         "media_start_in_sec":"0",
         "media_duration_format":"00:00:00",
         "media_thumbnail":"\/static\/img\/media\/live\/test-account_mid_000.jpg",
         "media_thumbnail_large":"\/static\/img\/media\/live\/test-account_large_000.jpg",
         "channel":{
            "followers":"7",
            "user_id":"278123",
            "user_name":"test-account",
            "user_status":"1",
            "user_logo":"\/static\/img\/channel\/test-account_53f4e837eb388_large.png",
            "user_cover":"\/static\/img\/channel\/cover_53fbf06572c78.png",
            "user_logo_small":"\/static\/img\/channel\/test-account_53f4e837eb388_small.png",
            "user_partner":null,
            "media_is_live":"0",
            "media_live_since":"2014-12-14 05:18:54",
            "twitter_account":"test-account",
            "twitter_enabled":"0",
            "livestream_count":"1",
            "channel_link":"http:\/\/hitbox.tv\/test-account"
         }
      }
   ]
}
```

If showHidden=false and stream is offline 

```json
no_media_found
```
