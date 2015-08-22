# Video API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /media/video/:channel/list](/media/video.md#get-mediavideouserlist) | Return VOD data |
| [GET /media/video/:media_id](/media/video.md#get-mediavideomedia_id) | Return VOD data |
| [POST /media/video/:channel](/media/video.md#post-mediavideochannel) | Create VOD from Recording |
| [PUT /media/video/:video_id](/media/video.md#put-mediavideovideo_id) | Updates VOD data |

## `GET /media/video/:channel/list`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| filter | No | recent,popular | Video Filter |
| hiddenOnly | No | boolean | Shows only private VODs |
| limit | No | integer | Default: 100 Max: ?; Limits amount of VODs given |
| publicOnly | No | boolean | Shows only public VODs only |
| search | No | string | Search titles of VODs |
| showHidden | No | boolean | Shows or Hide private VODs |
| yt | No | boolean | Shows only yt VODs |

Returns VOD list for the `:user`.

### Example URL

https://www.hitbox.tv/api/media/video/test-account/list

### Example Response 
```javascript
{
   "request":{
      "this":"/media/video/test-account/list"
   },
   "media_type":"video",
   "video":[
      {
         "media_user_name":"test-account",
         "media_id":"229802214",
         "media_type_id":"2",
         "media_user_id":"27873323",
         "media_category_id":"2433650",
         "media_file":"f7fad5547948ec921167c0cdsde7edd88c5d9f-53f8dcd26bc06",
         "media_profiles":"[{\"url\":\"\\/test-account\\/f7fad55432432ec921167c0c748cde7edd88c5d9f-53f8dcd26bc06\\/test-account\\/index.m3u8\",\"height\":\"720\",\"bitrate\":0}]",
         "media_host":null,
         "media_hosted_id":null,
         "media_rec_session":null,
         "media_ingest_host":null,
         "media_is_live":"1",
         "media_live_delay":"0",
         "media_featured":null,
         "media_privacy":null,
         "media_hidden":"1",
         "media_notify_users":"1",
         "media_date_added":"2014-08-23 18:36:54",
         "media_date_updated":null,
         "media_live_since":null,
         "media_mature":null,
         "media_live_notified":null,
         "media_key":"432432",
         "media_chat_enabled":"1",
         "media_deleted":null,
         "media_playing":"1",
         "media_transcoding":null,
         "media_recording":null,
         "media_dvr":"0",
         "media_countries":null,
         "media_info":null,
         "media_relay":null,
         "media_password_protected":null,
         "media_yt_upload":null,
         "media_yt_upload_status":null,
         "media_processing":null,
         "media_total_views":"8",
         "media_monthly_views":"2",
         "media_weekly_views":"0",
         "media_daily_views":"0",
         "media_featured_weight":null,
         "media_featured_forced":null,
         "media_featured_countries":null,
         "media_name":"f7fad55479432432432432432111de7edd88c5d9f-53f8dcd26bc06",
         "media_display_name":"test-account",
         "media_status":"Testing Microvolts - Aug 23rd #6",
         "media_title":"Testing Microvolts - Aug 23rd #6",
         "media_tags":"",
         "media_duration":"295.0000",
         "media_bg_image":null,
         "media_views":"8",
         "media_views_daily":"0",
         "media_views_weekly":"0",
         "media_views_monthly":"2",
         "category_id":"24650",
         "category_name":"MicroVolts",
         "category_name_short":null,
         "category_seo_key":"microvolts",
         "category_viewers":"2",
         "category_media_count":"1",
         "category_channels":null,
         "category_logo_small":null,
         "category_logo_large":"/static/img/games/2198350-microvolts_logo.jpg",
         "category_updated":"2014-12-13 20:40:22",
         "team_name":"TheBestTeam",
         "media_start_in_sec":"0",
         "media_download_link":"http://edge.bf.hitbox.tv/download//test-account/f7fad3232348ec921167c0c748cde7edd88c5d9f-53f8dcd26bc06/test-account/index.m3u8?h=1Wdqn7PSvlE8kWQKC4XICA&e=1418815005",
         "media_duration_format":"00:04:55",
         "media_thumbnail":"/static/img/media/videos/f7f/f7fad5547321312167c0c748cde7edd88c5d9f-53f8dcd26bc06_mid_000.jpg",
         "media_thumbnail_large":"/static/img/media/videos/f7f/f7fad5321328ec921167c0c748cde7edd88c5d9f-53f8dcd26bc06_large_000.jpg",
         "user_banned":null,
         "media_offline_id":null,
         "channel":{
            "followers":"7",
            "user_id":"21312",
            "user_name":"test-account",
            "user_status":"1",
            "user_logo":"/static/img/channel/test-account_53f4e837eb388_large.png",
            "user_cover":"/static/img/channel/cover_53fbf06572c78.png",
            "user_logo_small":"/static/img/channel/test-account_53f4e837eb388_small.png",
            "user_partner":null,
            "user_beta_profile": "1",
            "media_is_live":"0",
            "media_live_since":"2014-12-14 05:18:54",
            "user_media_id": "12",
            "twitter_account":"test-account",
            "twitter_enabled":"0",
            "livestream_count":"1"
         }
      }
   ]
}
```

## `GET /media/video/:media_id`

Return VOD data for the user. It's exactly the same as above except it returns a `media_description` value.

### Example URL

https://www.hitbox.tv/api/media/video/123

### Example Response
```javascript
{
   "request":{
      "this":"/media/video/123"
   },
   "media_type":"video",
   "video":[
      {
         "media_user_name":"test-account",
         "media_id":"123",
         "media_file":"f7fad5547948ec921167dac748cde7edd88c5d9f-53f8dcd26bc06",
         "media_user_id":"278723",
         "media_profiles":"[{\"url\":\"\\/test-account\\/f7fad5547948ec921das167c0c748cde7edd88c5d9f-53f8dcd26bc06\\/test-account\\/index.m3u8\",\"height\":\"720\",\"bitrate\":0}]",
         "media_type_id":"2",
         "media_is_live":"1",
         "media_live_delay":"0",
         "media_date_added":"2014-08-23 18:36:54",
         "media_live_since":null,
         "media_mature":null,
         "media_hidden":null,
         "media_transcoding":null,
         "media_chat_enabled":"1",
         "media_countries":null,
         "media_hosted_id":null,
         "user_banned":null,
         "media_name":"f7fad5547948ec921167c0c74das7edd88c5d9f-53f8dcd26bc06",
         "media_display_name":"test-account",
         "media_status":"This is a test video",
         "media_title":"This is a test video",
         "media_description":"",
         "media_description_md":null,
         "media_tags":"",
         "media_duration":"295.0000",
         "media_bg_image":null,
         "media_views":"8",
         "media_views_daily":"0",
         "media_views_weekly":"0",
         "media_views_monthly":"1",
         "category_id":"24650",
         "category_name":"MicroVolts",
         "category_name_short":null,
         "category_seo_key":"microvolts",
         "category_viewers":"2",
         "category_media_count":"1",
         "category_channels":null,
         "category_logo_small":null,
         "category_logo_large":"/static/img/games/2198350-microvolts_logo.jpg",
         "category_updated":"2014-12-13 20:40:22",
         "team_name":"TheBestTeam",
         "media_start_in_sec":"0",
         "media_duration_format":"00:04:55",
         "media_thumbnail":"/static/img/media/videos/f7f/f7fad5547948e543c0c748cde7edd88c5d9f-53f8dcd26bc06_mid_000.jpg",
         "media_thumbnail_large":"/static/img/media/videos/f7f/f7fad5547948ec9543c0c748cde7edd88c5d9f-53f8dcd26bc06_large_000.jpg",
         "media_offline_id":null,
         "channel":{
            "followers":"7",
            "user_id":"123",
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
            "livestream_count":"1"
         }
      }
   ]
}
```

## `POST /media/video/:channel`

Creates VOD from Recording object. `rec_session` can be retrieved from the [Recording API](/media/recordings.md). `clip_start` and `clip_duration` are where you want to cut in seconds.

### Example URL

https://www.hitbox.tv/api/media/video/test-account

### Example POST Payload

```javascript
{
   "user_name":"test-account",
   "authToken":"SuperSecret",
   "media_type":"video",
   "media_title":"This is a strean title! - Aug 6th #3",
   "media_status":"This is a stream title! - Aug 6th #3",
   "media_name":"test-account",
   "media_hidden":1,
   "media_category_id":{
      "category_id":"447",
      "category_name":"Quake Live",
      "category_name_short":null,
      "category_seo_key":"quake-live",
      "category_viewers":"0",
      "category_media_count":"1",
      "category_channels":null,
      "category_logo_small":null,
      "category_logo_large":"/static/img/games/293456-quakelive2.jpg",
      "category_updated":"2015-08-06 02:21:12"
   },
   "clip_duration":23.658077999999996,
   "clip_start":8.76451,
   "rec_session":"d4ae1ceb9f3849f14bgfdyhtr8734fdsa3e695-55c2b7e5c981a",
   "original":false
}
```

### Example Response

Successful
```
{
  "media_id":"487354"
}
```

Failed (Title too short, rec_session incorrect, etc)

```javascript
{
    "error":true,
    "error_msg":"media_error",
    "success":false
}
```

## `PUT /media/video/:video_id`

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | Users Auth Token. | 

Updates VOD data.

**Caution**: To correctly update this API, You must send **all** values below except `media_description` which is optional unless you want to update the video description.

### Example URL

https://www.hitbox.tv/api/media/video/123

### Example PUT Payload

```javascript
{
  "video":[
    {
      "media_user_name":"test-account",
      "media_id":"481290",
      "media_category_id":"24146",
      "media_hidden":"0",
      "media_status":"This is a video title!",
      "media_description":""
    }
  ]
}
```

### Example Response 

```javascript
{
  "video":[
    {
      "media_user_name":"masta",
      "media_id":"481290",
      "media_category_id":"24146",
      "media_hidden":"0",
      "media_status":"This is a video title!",
      "media_description":""
    }
  ],
  "livestream":[
    {
      "media_description_md":null
    }
  ]
}
```
