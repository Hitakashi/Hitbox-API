# Media Info API
***
*Partner Channels Only*

| Endpoint | Description |
| ---- | --------------- |
| [GET /mediainfo/live/:media_id](/media/mediainfo.md#get-mediainfolivemedia_id) | Return video stats. |

## `GET /mediainfo/live/:media_id`

Returns video information for `media_id`

### Example URL

https://www.hitbox.tv/api/mediainfo/live/123

### Example Response 

```javascript
{
   "request":{
      "this":"/mediainfo/live/123"
   },
   "mediainfo":{
      "log_id":"102099",
      "media_id":"123",
      "width":"1440",
      "height":"900",
      "vbitrate":"2048000",
      "abitrate":"98304",
      "vcodec":"h264",
      "acodec":"aac",
      "profile":"High",
      "level":"40",
      "fps":"30",
      "gop":null,
      "hostname":"WAS-BCE1-BL04",
      "useragent":null,
      "log_date":"2014-12-18 07:42:49"
   }
}
```
