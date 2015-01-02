# Player Config API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /player/config/live/:channel](/player/config/live/index.md#get-) | Returns stream stats |

## `GET /player/config/live/:channel`

Returns video player information, could be useful to some people.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | No | string | User's Auth Token |
| redis | ? | boolean | ? |
| embed | ? | boolean | ? |
| qos | ? | boolean | ? |
| showHidden | Yes | boolean | Technically not required, but it will show no user info if the channel is offline. |

### Example URL

https://www.hitbox.tv/api/player/config/live/test-account

### Example Response 

```json
{
   "key":"#$54d46ea213123213979",
   "play":null,
   "clip":{
      "autoPlay":true,
      "autoBuffering":true,
      "bufferLength":"2",
      "eventCategory":"test-account\/live\/278723",
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
      "adsPlayed":false
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
         "hls_maxbufferlength":60,
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
      "pingback":{
         "url":"flowplayer.pingback-3.2.7.swf",
         "server_url":"http:\/\/api.mawire.com\/pingback",
         "video_id":"1",
         "wsUrl":"ws:\/\/54.205.241.225\/viewers",
         "wsChannel":"test-account",
         "wsToken":"312312312312321321312312",
         "userName":"test-account",
         "uuid":"312312312312321321312312",
         "countryCode":"",
         "debug":true,
         "viewersPluginName":"viewers",
         "infoPluginName":"info",
         "ovaPluginName":"ova",
         "isSubscriber":false,
         "isFollower":true,
         "updateTimeout":1000,
         "embed":false
      },
      "controls":null,
      "info":{
         "display":"none",
         "url":"flowplayer.content-3.2.8.swf",
         "html":"<\/p>",
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
         "LR_PUBLISHER_ID":208741,
         "LR_SCHEMA":"vast2-vpaid",
         "LR_ADUNIT":"in",
         "LR_VIDEO_POSITION":0,
         "LR_AUTOPLAY":1,
         "LR_CONTENT":6,
         "LR_TITLE":"test-account",
         "LR_VIDEO_ID":"18730",
         "LR_MUTED":0,
         "CACHEBUSTER":1420167259,
         "TIMESTAMP":1420167259,
         "LR_LAYOUT_SKIN_MESSAGE":"Advertisement: Stream will resume in {COUNTDOWN} seconds.",
         "LR_LIVESTREAM":1,
         "LR_LAYOUT_SKIN_ID":2,
         "LR_LAYOUT_LINEAR_PAUSEONCLICKTHRU":0,
         "LR_BITRATE":"high",
         "LR_VIDEO_URL":"http:\/\/www.hitbox.tv\/test-account",
         "LR_DESCRIPTION":"test-account",
         "LR_IP":"X.X.X.X"
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
         "netConnectionUrl":"rtmp:\/\/hitboxna06livefs.fplive.net\/hitboxna06live-live",
         "rtmpSubscribe":true,
         "bitrates":[
            {
               "url":"stream_test-account",
               "bitrate":3500,
               "label":"Source",
               "isDefault":true,
               "provider":"rtmp"
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
      "max_buffer_count":"6",
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