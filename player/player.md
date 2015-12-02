# Player API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /player/server](/player/player.md#get-playerserver) | Returns socket server addresses. |
| [GET /player/config/live/:media_id](/player/player.md#get-playerconfiglivemedia_id) | Returns live player config. |
| [GET /player/config/video/:video_id](/player/player.md#get-playerconfigvideovideo_id) | Returns VOD player config. |
| [GET /player/reconfig/:channe/:rec_session](/player/player.md#get-playerrecconfigchannelrec_session) | Returns player config for recordings. |

## `GET /player/server`

Returns socket server addresses.

### Example URL

https://www.hitbox.tv/api/player/server

### Example Response

```javascript
[
   {
      "server_ip":"ec2-54-226-44-62.compute-1.amazonaws.com"
   },
   {
      "server_ip":"ec2-54-144-24-130.compute-1.amazonaws.com"
   },
   {
      "server_ip":"ec2-54-234-100-106.compute-1.amazonaws.com"
   },
   {
      "server_ip":"ec2-50-17-115-203.compute-1.amazonaws.com"
   },
   {
      "server_ip":"ec2-54-144-94-47.compute-1.amazonaws.com"
   }
]
```

## `GET /player/config/live/:media_id`

Returns player config for livestream.  
`media_id` can be replaced with `channel`.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | No | string | User's Auth Token |
| redis | No | boolean | Unknown, Default: true |
| embed | No | boolean | Show channel url, Default: false |
| qos | No | boolean | Show qosmonitor and bwcheck, Default: false |
| showHidden | No | boolean | Show Hidden Streams. |

### Example URL

https://www.hitbox.tv/api/player/config/live/436009  
https://www.hitbox.tv/api/player/config/live/test-account

### Example Response

```javascript
{
    "key":"#$54d46eaa112f0508979",
    "play":null,
    "clip":{
        "autoPlay":true,
        "autoBuffering":true,
        "bufferLength":"2",
        "eventCategory":"Hitakashi/live/278723",
        "baseUrl":null,
        "url":"/api/player/hls/hitakashi.m3u8",
        "stopLiveOnPause":true,
        "live":true,
        "smoothing":true,
        "provider":"hls",
        "scaling":"fit",
        "bitrates":[
            {
                "url":"hitakashi_360p",
                "bitrate":500,
                "fps":"",
                "label":"360p",
                "qlabel":"",
                "provider":"rtmpHitbox",
                "isDefault":false
            },
            {
                "url":"hitakashi_480p",
                "bitrate":1000,
                "fps":"",
                "label":"480p",
                "qlabel":"",
                "provider":"rtmpHitbox",
                "isDefault":false
            },
            {
                "url":"hitakashi",
                "bitrate":3500,
                "fps":30,
                "label":"720p",
                "qlabel":"HD",
                "isDefault":true,
                "provider":"rtmpHitbox"
            },
            {
                "url":"http://api.hitbox.tv/player/hls/hitakashi.m3u8",
                "bitrate":5000,
                "label":"Auto",
                "isDefault":false,
                "provider":"hls",
                "abr":true
            }
        ],
        "controls":false,
        "type":"video",
        "adsPlayed":false
    },
    "playlist":[
        {
            "provider":"rtmp",
            "netConnectionUrl":"rtmp://edge.live.hitbox.tv/live",
            "rtmpSubscribe":false,
            "bitrates":[
                {
                    "url":"hitakashi_360p",
                    "bitrate":500,
                    "fps":"",
                    "label":"360p",
                    "qlabel":"",
                    "provider":"rtmpHitbox",
                    "isDefault":false
                },
                {
                    "url":"hitakashi_480p",
                    "bitrate":1000,
                    "fps":"",
                    "label":"480p",
                    "qlabel":"",
                    "provider":"rtmpHitbox",
                    "isDefault":false
                },
                {
                    "url":"hitakashi",
                    "bitrate":3500,
                    "fps":30,
                    "label":"720p",
                    "qlabel":"HD",
                    "isDefault":true,
                    "provider":"rtmpHitbox"
                },
                {
                    "url":"/api/player/hls/hitakashi.m3u8",
                    "bitrate":5000,
                    "label":"Auto",
                    "isDefault":false,
                    "provider":"hls",
                    "abr":true
                }
            ]
        }
    ],
    "plugins":{
        "rtmp":{
            "url":"flowplayer.rtmp-3.2.12.1.swf",
            "netConnectionUrl":"rtmp://edge.live.hitbox.tv/live",
            "reconnecting":true
        },
        "hls":{
            "url":"flashlsFlowPlayer.swf",
            "hls_lowbufferlength":1,
            "hls_minbufferlength":4,
            "hls_maxbufferlength":24,
            "hls_startfromlowestlevel":true,
            "hls_seekfromlowestlevel":true,
            "hls_live_flushurlcache":false,
            "hls_seekmode":"KEYFRAME",
            "hls_usehardwarevideodecoder":false
        },
        "rtmpHitbox":{
            "url":"flowplayer.rtmp-3.2.12.1.swf",
            "netConnectionUrl":"rtmp://edge.live.hitbox.tv/live",
            "reconnecting":true
        },
        "pingback":{
            "url":"flowplayer.pingback-3.2.7.swf",
            "server_url":"http://api.mawire.com/pingback",
            "video_id":"1",
            "wsUrl":"ws://ec2-184-72-187-230.compute-1.amazonaws.com/viewers",
            "wsChannel":"hitakashi",
            "wsToken":"",
            "userName":"Hitakashi",
            "uuid":"bc001b0e765ee5848f58d4e9e9491028b8ffce3c",
            "countryCode":"US",
            "debug":false,
            "viewersPluginName":"viewers",
            "infoPluginName":"info",
            "ovaPluginName":"ova",
            "isSubscriber":false,
            "isFollower":false,
            "isWhitelabel":false,
            "updateTimeout":1000,
            "embed":false,
            "ip":"x.x.x.x",
            "cdn_id":"1"
        },
        "controls":null,
        "info":{
            "display":"none",
            "url":"flowplayer.content-3.2.8.swf",
            "html":"<p align=\"center\"></p>",
            "width":"50%",
            "height":30,
            "backgroundColor":"#1A1A1A",
            "backgroundGradient":"none",
            "opacity":"1",
            "borderRadius":10,
            "borderColor":"#999999",
            "border":0,
            "color":"#FFFFFF",
            "bottom":60,
            "zIndex":"10",
            "closeButton":true,
            "style":{
                "p":{
                    "fontSize":16,
                    "fontFamily":"verdana,arial,helvetica",
                    "fontWeight":"normal"
                }
            }
        },
        "gatracker":{
            "url":"flowplayer.analytics-3.2.9.1.swf",
            "event":{
                "all":true
            },
            "debug":false,
            "accountId":"UA-42900118-2"
        },
        "ova":{
            "url":"flowplayer.liverail-3.2.7.4.swf",
            "LR_PUBLISHER_ID":20341,
            "LR_SCHEMA":"vast2-vpaid",
            "LR_ADUNIT":"in",
            "LR_VIDEO_POSITION":0,
            "LR_AUTOPLAY":1,
            "LR_CONTENT":6,
            "LR_TITLE":"hitakashi",
            "LR_VIDEO_ID":"15830",
            "LR_MUTED":0,
            "CACHEBUSTER":1449086743,
            "TIMESTAMP":1449086743,
            "LR_TAGS":"mediaUserId_278723,categoryId_424",
            "LR_LAYOUT_SKIN_MESSAGE":"Advertisement: Stream will resume in {COUNTDOWN} seconds.",
            "LR_LIVESTREAM":1,
            "LR_LAYOUT_SKIN_ID":2,
            "LR_LAYOUT_LINEAR_PAUSEONCLICKTHRU":0,
            "LR_BITRATE":"high",
            "LR_VIDEO_URL":"http://www.hitbox.tv/hitakashi",
            "LR_DESCRIPTION":"hitakashi",
            "LR_IP":"x.x.x.x"
        }
    },
    "cdns":[
        {
            "provider":"rtmp",
            "netConnectionUrl":"rtmp://edge.live.hitbox.tv/live",
            "rtmpSubscribe":false,
            "bitrates":[
                {
                    "url":"hitakashi_360p",
                    "bitrate":500,
                    "fps":"",
                    "label":"360p",
                    "qlabel":"",
                    "provider":"rtmpHitbox",
                    "isDefault":false
                },
                {
                    "url":"hitakashi_480p",
                    "bitrate":1000,
                    "fps":"",
                    "label":"480p",
                    "qlabel":"",
                    "provider":"rtmpHitbox",
                    "isDefault":false
                },
                {
                    "url":"hitakashi",
                    "bitrate":3500,
                    "fps":30,
                    "label":"720p",
                    "qlabel":"HD",
                    "isDefault":true,
                    "provider":"rtmpHitbox"
                },
                {
                    "url":"/api/player/hls/hitakashi.m3u8",
                    "bitrate":5000,
                    "label":"Auto",
                    "isDefault":false,
                    "provider":"hls",
                    "abr":true
                }
            ]
        },
        {
            "provider":"rtmp",
            "netConnectionUrl":"rtmp://hitboxna06livefs.fplive.net/hitboxna06live-live",
            "rtmpSubscribe":true,
            "bitrates":[
                {
                    "url":"stream_hitakashi_360p",
                    "bitrate":500,
                    "fps":"",
                    "label":"360p",
                    "qlabel":"",
                    "provider":"rtmp",
                    "isDefault":false
                },
                {
                    "url":"stream_hitakashi_480p",
                    "bitrate":1000,
                    "fps":"",
                    "label":"480p",
                    "qlabel":"",
                    "provider":"rtmp",
                    "isDefault":false
                },
                {
                    "url":"stream_hitakashi",
                    "bitrate":3500,
                    "fps":30,
                    "label":"720p",
                    "qlabel":"HD",
                    "isDefault":true,
                    "provider":"rtmp"
                },
                {
                    "url":"/api/player/hls/hitakashi.m3u8",
                    "bitrate":5000,
                    "label":"Auto",
                    "isDefault":false,
                    "provider":"hls",
                    "abr":true
                }
            ]
        },
        {
            "provider":"rtmpHitbox",
            "netConnectionUrl":"rtmp://edge.live.hitbox.tv/live",
            "rtmpSubscribe":false,
            "bitrates":[
                {
                    "url":"hitakashi_360p",
                    "bitrate":500,
                    "fps":"",
                    "label":"360p",
                    "qlabel":"",
                    "provider":"rtmpHitbox",
                    "isDefault":false
                },
                {
                    "url":"hitakashi_480p",
                    "bitrate":1000,
                    "fps":"",
                    "label":"480p",
                    "qlabel":"",
                    "provider":"rtmpHitbox",
                    "isDefault":false
                },
                {
                    "url":"hitakashi",
                    "bitrate":3500,
                    "fps":30,
                    "label":"720p",
                    "qlabel":"HD",
                    "isDefault":true,
                    "provider":"rtmpHitbox"
                },
                {
                    "url":"http://api.hitbox.tv/player/hls/hitakashi.m3u8",
                    "bitrate":5000,
                    "label":"Auto",
                    "isDefault":false,
                    "provider":"hls",
                    "abr":true
                }
            ]
        }
    ],
    "canvas":{
        "backgroundGradient":"none"
    },
    "log":{
        "level":"debug",
        "filter":"org.osmf*"
    },
    "showErrors":false,
    "settings":{
        "media_id":"-1",
        "max_buffer_count":"3",
        "buffer_length":"2",
        "max_roundtrips":"3",
        "reset_timeout":"60000",
        "play_timeout":"15000",
        "start_timeout":"10000",
        "ad_plugin":"liverail-off",
        "default_br":null,
        "enabled":"1",
        "no_prerolls":null,
        "delBitrates":[

        ]
    }
}
```


## `GET /player/config/video/:video_id`

Returns player config for VOD.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | No | string | User's Auth Token |
| redis | No | boolean | Unknown, Default: true |
| embed | No | boolean | Show channel url, Default: false |
| qos | No | boolean | Show qosmonitor and bwcheck, Default: false |
| showHidden | No | boolean | Show Hidden Streams. |

### Example URL

https://www.hitbox.tv/api/player/config/video/123456

### Example Response

```javascript
{
    "key":"#$54d46eaa112f0508979",
    "play":null,
    "clip":{
        "autoPlay":true,
        "autoBuffering":true,
        "bufferLength":"2",
        "eventCategory":"Hitakashi/video/278723",
        "baseUrl":null,
        "url":"/api/player/hlsvod/778941.m3u8",
        "stopLiveOnPause":true,
        "live":false,
        "smoothing":true,
        "provider":"pseudo",
        "scaling":"fit",
        "bitrates":[
            {
                "url":"http://edge.hls.vods.hitbox.tv/static/videos/vods/hitakashi/c3da94b685b66e1e4402cf7bd6a706bb44347ab3/hitakashi_360p/index.m3u8",
                "bitrate":500,
                "fps":"",
                "label":"360p",
                "qlabel":"",
                "provider":"pseudo",
                "isDefault":true
            },
            {
                "url":"http://edge.hls.vods.hitbox.tv/static/videos/vods/hitakashi/c3da94b685b66e1e4402cf7bd6a706bb44347ab3/hitakashi_480p/index.m3u8",
                "bitrate":1000,
                "fps":"",
                "label":"480p",
                "qlabel":"",
                "provider":"pseudo",
                "isDefault":false
            },
            {
                "url":"/api/player/hlsvod/778941.m3u8",
                "bitrate":5000,
                "label":"Auto",
                "isDefault":false,
                "provider":"pseudo",
                "abr":true
            }
        ],
        "controls":false,
        "type":"video",
        "adsPlayed":false
    },
    "plugins":{
        "pseudo":{
            "url":"flashlsFlowPlayer.swf",
            "hls_debug":false,
            "hls_debug2":false,
            "hls_lowbufferlength":5,
            "hls_minbufferlength":10,
            "hls_maxbufferlength":60,
            "hls_startfromlowestlevel":true,
            "hls_seekfromlowestlevel":false,
            "hls_live_flushurlcache":false,
            "hls_seekmode":"SEGMENT"
        },
        "controls":null,
        "info":{
            "display":"none",
            "url":"flowplayer.content-3.2.8.swf",
            "html":"<p align=\"center\"></p>",
            "width":"50%",
            "height":30,
            "backgroundColor":"#1A1A1A",
            "backgroundGradient":"none",
            "opacity":"1",
            "borderRadius":10,
            "borderColor":"#999999",
            "border":0,
            "color":"#FFFFFF",
            "bottom":60,
            "zIndex":"10",
            "closeButton":true,
            "style":{
                "p":{
                    "fontSize":16,
                    "fontFamily":"verdana,arial,helvetica",
                    "fontWeight":"normal"
                }
            }
        },
        "gatracker":{
            "url":"flowplayer.analytics-3.2.9.1.swf",
            "event":{
                "all":true
            },
            "debug":false,
            "accountId":"UA-42900118-2"
        },
        "ova":{
            "url":"flowplayer.liverail-3.2.7.4.swf",
            "LR_PUBLISHER_ID":20341,
            "LR_SCHEMA":"vast2-vpaid",
            "LR_ADUNIT":"in",
            "LR_VIDEO_POSITION":0,
            "LR_AUTOPLAY":1,
            "LR_CONTENT":6,
            "LR_TITLE":"c3da94b685b66e1e4402cf7bd6a706bb44347ab3",
            "LR_VIDEO_ID":"778941",
            "LR_MUTED":0,
            "CACHEBUSTER":1449085606,
            "TIMESTAMP":1449085606,
            "LR_TAGS":"mediaUserId_278723",
            "LR_LAYOUT_SKIN_MESSAGE":"Advertisement: Stream will resume in {COUNTDOWN} seconds.",
            "LR_LIVESTREAM":1,
            "LR_LAYOUT_SKIN_ID":2,
            "LR_LAYOUT_LINEAR_PAUSEONCLICKTHRU":0,
            "LR_BITRATE":"high",
            "LR_VIDEO_URL":"http://www.hitbox.tv/video/778941",
            "LR_DESCRIPTION":"c3da94b685b66e1e4402cf7bd6a706bb44347ab3",
            "LR_IP":"x.x.x.x"
        }
    },
    "canvas":{
        "backgroundGradient":"none"
    },
    "log":{
        "level":"debug",
        "filter":"org.osmf*"
    },
    "showErrors":false,
    "settings":{
        "media_id":"-1",
        "max_buffer_count":"3",
        "buffer_length":"2",
        "max_roundtrips":"3",
        "reset_timeout":"60000",
        "play_timeout":"15000",
        "start_timeout":"10000",
        "ad_plugin":"liverail-off",
        "default_br":null,
        "enabled":"1",
        "no_prerolls":null
    },
    "playlist":[

    ]
}
```

## `GET /player/recconfig/:channel/:rec_session`

Returns player config for recordings. `rec_session` can be taken from the [recording](/video/recordings.md) API.

### Example URL

https://www.hitbox.tv/api/player/recconfig/test-account/312312312321312321312312312312-54b3122b336c7

### Example Response

```javascript
{
   "key":"#$54d46eaa11fsdfdsf32279",
   "play":null,
   "clip":{
      "autoPlay":true,
      "autoBuffering":true,
      "url":"http://edge.hls.vods.hitbox.tv/static/videos/vods/test-account/bb9304c4951edasdasdas02a5a937e527ac196-54b3122b336c7/test-account/index.m3u8",
      "provider":"httpstreaming",
      "scaling":"fit",
      "start":1
   },
   "plugins":{
      "controls":null,
      "httpstreaming":{
         "url":"flashlsFlowPlayer.swf",
         "hls_debug":false,
         "hls_debug2":false,
         "hls_lowbufferlength":1,
         "hls_minbufferlength":3,
         "hls_maxbufferlength":60,
         "hls_startfromlowestlevel":false,
         "hls_seekfromlowestlevel":false,
         "hls_live_flushurlcache":false,
         "hls_seekmode":"SEGMENT"
      }
   },
   "canvas":{
      "backgroundGradient":"none"
   },
   "log":{
      "level":"debug",
      "filter":"org.osmf.*, org.electroteque.m3u8.*, org.flowplayer.bitrateselect.*"
   }
}
```
