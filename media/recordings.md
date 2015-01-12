# Recording API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /recordings/:channel](/media/recordings.md#get-recordingschannel) | Return recordings for the channel. |

## `GET /recordings/:channel`

Returns recordings for the channel.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| limit | No | Integer | limit of recordings |
| search | No | string | search recording (name) |

### Example URL

https://www.hitbox.tv/api/recordings/test-account?authToken=123

### Example Response 

```json
[
   {
      "rec_id":"199025512",
      "rec_media_id":"1524830",
      "rec_session":"0e61e00563c9b3239a0ee4c234812950d0784c24728-548bf4333a43867",
      "rec_title":"Mobile Suit Gundam Online 1 - Dec 13th #4",
      "rec_category_id":"28442",
      "rec_path":"\/static\/videos\/vods\/test-account\/0e61e00563c9b3239a0ee4c812950d0784c24728-548bf4333a867\/test-account\/index.m3u8",
      "rec_name":"test-account",
      "rec_addr":"WAS-BCE1-BL06",
      "rec_info":{
         "index":0,
         "codec_name":"h264",
         "codec_long_name":"H.264 \/ AVC \/ MPEG-4 AVC \/ MPEG-4 part 10",
         "profile":"High",
         "codec_type":"video",
         "codec_time_base":"1\/60",
         "codec_tag_string":"[27][0][0][0]",
         "codec_tag":"0x001b",
         "width":1920,
         "height":1080,
         "has_b_frames":2,
         "sample_aspect_ratio":"0:1",
         "display_aspect_ratio":"0:1",
         "pix_fmt":"yuv420p",
         "level":40,
         "r_frame_rate":"30\/1",
         "avg_frame_rate":"15\/1",
         "time_base":"1\/90000",
         "start_pts":311670,
         "start_time":"3.463000",
         "disposition":{
            "default":0,
            "dub":0,
            "original":0,
            "comment":0,
            "lyrics":0,
            "karaoke":0,
            "forced":0,
            "hearing_impaired":0,
            "visual_impaired":0,
            "clean_effects":0,
            "attached_pic":0
         }
      },
      "rec_height":"1080",
      "rec_bitrate":"83",
      "rec_duration":"00:00:19",
      "rec_date_added":"2014-12-13 08:07:57",
      "rec_saved_media_id":null,
      "thumbnail":"\/static\/img\/media\/videos\/0e6\/0e61e00563c9b3239a0ee433c812950d0784c243728-548bf4333a867_mid_000.jpg",
      "thumbnail_large":"\/static\/img\/media\/videos\/0e6\/0e61e005633c9b3239a330ee4c812950d0784c24728-548bf4333a867_large_000.jpg",
      "rec_duration_sec":"19.3700",
      "rec_download_link":"http:\/\/edge.bf.hitbox.tv\/download\/index.m3u8?h=zLrNdpX33DNTlp_1L3Ke1pkpA&e=1418811941"
   }
]
```
