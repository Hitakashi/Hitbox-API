# Player API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /player/server](/player/player.md#get-playerconfiglivemedia_id) | Returns socket server addresses. |
| [GET /player/config/live/:media_id](/player/player.md#get-playerconfiglivemedia_id) | Returns live player config. |
| [GET /player/config/video/:video_id](/player/player.md#get-playerconfigvideovideo_id) | Returns VOD player config. |

## `GET /player/server`

Returns socket server addresses.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | No | string | User's Auth Token |

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

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | No | string | User's Auth Token |
| redis | No | boolean | Unknown, Default: true |
| embed | No | boolean | Show channel url, Default: false |
| qos | No | boolean | Show qosmonitor and bwcheck, Default: false |
| showHidden | No | boolean | Show Hidden Streams. |

### Example URL

https://www.hitbox.tv/api/player/config/live/123456

### Example Response

```javascript
{
   "key":"#$0123456789abcdef012",
   "play":null,
   "clip":{
      "autoPlay":true,
      "autoBuffering":true,
      "bufferLength":"2",
      "eventCategory":"Test-Account\/live\/1728027",
      "baseUrl":null,
      "url":"test-account",
      "stopLiveOnPause":true,
      "live":true,
      "smoothing":true,
      "provider":"rtmp",
      "scaling":"fit",
      "bitrates":[
         {
            "url":"test-account",
            "bitrate":3500,
            "label":"Source",
            "isDefault":true,
            "provider":"rtmpHitbox"
         }
      ],
      "controls":false,
      "type":"video",
      "adsPlayed":false,
      "linkWindow":"_blank",
      "linkUrl":"http:\/\/hitbox.tv\/test-account"
   },
   "playlist":[
      {
         "provider":"rtmp",
         "netConnectionUrl":"rtmp:\/\/fml.B6BF.edgecastcdn.net\/20B6BF",
         "rtmpSubscribe":true,
         "bitrates":[
            {
               "url":"test-account",
               "bitrate":3500,
               "label":"Source",
               "isDefault":true,
               "provider":"rtmp"
            }
         ]
      }
   ],
   "plugins":{
      "rtmp":{
         "url":"flowplayer.rtmp-3.2.12.1.swf",
         "netConnectionUrl":"rtmp:\/\/edge.live.hitbox.tv\/live",
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
         "netConnectionUrl":"rtmp:\/\/edge.live.hitbox.tv\/live",
         "reconnecting":true
      },
      "bwcheck":{
         "url":"flowplayer.bwcheck-3.2.12.1.swf"
      },
      "qos":{
         "url":"flowplayer.qosmonitor.swf",
         "stats":{
            "all":true
         },
         "info":true
      },
      "pingback":{
         "url":"flowplayer.pingback-3.2.7.swf",
         "server_url":"http:\/\/api.mawire.com\/pingback",
         "video_id":"1",
         "wsUrl":"ws:\/\/ec2-50-17-115-203.compute-1.amazonaws.com\/viewers",
         "wsChannel":"test-account",
         "wsToken":"",
         "userName":"",
         "uuid":"",
         "countryCode":"DE",
         "debug":true,
         "viewersPluginName":"viewers",
         "infoPluginName":"info",
         "ovaPluginName":"ova",
         "isSubscriber":false,
         "isFollower":null,
         "isWhitelabel":false,
         "updateTimeout":1000,
         "embed":true,
         "ip":"x.x.x.x",
         "cdn_id":"2"
      },
      "controls":null,
      "info":{
         "display":"none",
         "url":"flowplayer.content-3.2.8.swf",
         "html":"

<\/p>",
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
         "accountId":"UA-12345678-9"
      },
      "ova":{
         "url":"flowplayer.liverail-3.2.7.4.swf",
         "LR_PUBLISHER_ID":20341,
         "LR_SCHEMA":"vast2-vpaid",
         "LR_ADUNIT":"in",
         "LR_VIDEO_POSITION":0,
         "LR_AUTOPLAY":1,
         "LR_CONTENT":6,
         "LR_TITLE":"test-account",
         "LR_VIDEO_ID":"436009",
         "LR_MUTED":0,
         "CACHEBUSTER":1439665272,
         "TIMESTAMP":1439665272,
         "LR_TAGS":"mediaUserId_",
         "LR_LAYOUT_SKIN_MESSAGE":"Advertisement: Stream will resume in {COUNTDOWN} seconds.",
         "LR_LIVESTREAM":1,
         "LR_LAYOUT_SKIN_ID":2,
         "LR_LAYOUT_LINEAR_PAUSEONCLICKTHRU":0,
         "LR_BITRATE":"high",
         "LR_VIDEO_URL":"http:\/\/www.hitbox.tv\/test-account",
         "LR_DESCRIPTION":"test-account",
         "LR_IP":"x.x.x.x"
      }
   },
   "cdns":[
      {
         "provider":"rtmp",
         "netConnectionUrl":"rtmp:\/\/fml.B6BF.edgecastcdn.net\/20B6BF",
         "rtmpSubscribe":true,
         "bitrates":[
            {
               "url":"test-account",
               "bitrate":3500,
               "label":"Source",
               "isDefault":true,
               "provider":"rtmp"
            }
         ]
      },
      {
         "provider":"rtmp",
         "netConnectionUrl":"rtmp:\/\/edge.live.hitbox.tv\/live",
         "rtmpSubscribe":false,
         "bitrates":[
            {
               "url":"test-account",
               "bitrate":3500,
               "label":"Source",
               "isDefault":true,
               "provider":"rtmpHitbox"
            }
         ]
      },
      {
         "provider":"rtmpHitbox",
         "netConnectionUrl":"rtmp:\/\/edge.live.hitbox.tv\/live",
         "rtmpSubscribe":false,
         "bitrates":[
            {
               "url":"test-account",
               "bitrate":3500,
               "label":"Source",
               "isDefault":true,
               "provider":"rtmpHitbox"
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
   "key":"#$0123456789abcdef012",
   "play":null,
   "clip":{
      "autoPlay":true,
      "autoBuffering":true,
      "bufferLength":"2",
      "eventCategory":"\/video\/",
      "baseUrl":null,
      "url":"\/api\/player\/hlsvod\/436009.m3u8",
      "stopLiveOnPause":true,
      "live":false,
      "smoothing":true,
      "provider":"pseudo",
      "scaling":"fit",
      "bitrates":[
         {
            "url":"http:\/\/edge.hls.vods.hitbox.tv\/static\/videos\/vods\/Test-Account\/0123456789abcdef0123456789abcdef01234567-0123456789abc_0123456789abc\/Test-Account\/index.m3u8",
            "bitrate":0,
            "label":"HD 720p",
            "provider":"pseudo",
            "isDefault":true
         },
         {
            "url":"\/api\/player\/hlsvod\/436009.m3u8",
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
         "html":"

<\/p>",
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
         "accountId":"UA-12345678-9"
      },
      "ova":{
         "url":"flowplayer.liverail-3.2.7.4.swf",
         "LR_PUBLISHER_ID":20341,
         "LR_SCHEMA":"vast2-vpaid",
         "LR_ADUNIT":"in",
         "LR_VIDEO_POSITION":0,
         "LR_AUTOPLAY":1,
         "LR_CONTENT":6,
         "LR_TITLE":"0123456789abcdef0123456789abcdef01234567-0123456789abc_0123456789abc",
         "LR_VIDEO_ID":"436009",
         "LR_MUTED":0,
         "CACHEBUSTER":1439666328,
         "TIMESTAMP":1439666328,
         "LR_TAGS":"mediaUserId_",
         "LR_LAYOUT_SKIN_MESSAGE":"Advertisement: Stream will resume in {COUNTDOWN} seconds.",
         "LR_LIVESTREAM":1,
         "LR_LAYOUT_SKIN_ID":2,
         "LR_LAYOUT_LINEAR_PAUSEONCLICKTHRU":0,
         "LR_BITRATE":"high",
         "LR_VIDEO_URL":"http:\/\/www.hitbox.tv\/video\/436009",
         "LR_DESCRIPTION":"0123456789abcdef0123456789abcdef01234567-0123456789abc_0123456789abc",
         "LR_IP":"81.217.18.106"
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
      "enabled":"1"
   },
   "playlist":[

   ]
}
```