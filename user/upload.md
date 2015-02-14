# Upload Account Avatar
***

I won't document each and every API payload as they are all similar. I will add each API endpoint to table.

| Endpoint | Description |
| ---- | --------------- |
| [POST /upload/account/:user/:auth](/user/upload.md#post-uploadaccountuserauth) | Changes a users avatar. |
| [POST /upload/account/:channel/:auth](/user/upload.md#get-uploaddescriptionchannelauth) | Changes channel banners. |
| [GET /upload/description/:channe/:auth](/user/upload.md#get-uploaddescriptionchannelauth) | Returns images uploaded for profile description use |
| [POST /upload/description/:channel/:auth](/user/upload.md#post-uploaddescriptionchannelauth) | Uploads images for profile description use |
| [DELETE /upload/description/:channel/:auth](/user/upload.md#delete-uploaddescriptionchannelauth) | Deletes imagees for profile description use |
| [POST /upload/team/:username/:auth](/user/upload.md#post-uploadteamusernameauth) | Uploads teams images |

## `POST /upload/account/:user/:auth`

Update User Avatar.

### Example URL

https://www.hitbox.tv/api/upload/account/test-account/12356765756756

### Example Payload 

```
------WebKitFormBoundaryXXXXXXXX
Content-Disposition: form-data; name="file"; filename="hitbox_profile_picture.png"
Content-Type: image/png


------WebKitFormBoundaryXXXXXXXX--
```

### Header

```
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryXXXXXXXX
```

## `POST /upload/account/:channel/:auth`

### Example URL

https://www.hitbox.tv/api/upload/account/test-account/1237865864534342423

### Example Payload

```
------WebKitFormBoundaryxc5Hjc4MDXrAqZX6
Content-Disposition: form-data; name="cover"; filename="test-account-profile_image-054b5323232430b-300x300.png"
Content-Type: image/png


------WebKitFormBoundaryxc5Hjc4MDXrAqZX6--
```

### Header

```json
Content-Type:multipart/form-data; boundary=----WebKitFormBoundaryxc5Hjc4MDXrAqZX6
```

### Example Response

```json
{
    "cover":"\/static\/img\/channel\/cover_54b72f19e8765.png"
}
```

## `GET /upload/description/:channel/:auth`

### Example URL

https://www.hitbox.tv/api/upload/description/test-account/1232131232132

### Example Response 

```json
[
    {
        "image_id":"123",
        "image_path":"\/static\/img\/channel\/test-account-profile-image-054b2d1096530c0b-300x300-png_54b7309baa686.png",
        "image_date_added":"2015-01-14 23:49:45"
    }
]
```

## `POST /upload/description/:channel/:auth`

### Example URL

http://www.hitbox.tv/api/upload/description/test-account/1232132132131

### Example Payload

```json
------WebKitFormBoundarybwSxxcx5yC7Zsn2G
Content-Disposition: form-data; name="file"; filename="editor.png"
Content-Type: image/png


------WebKitFormBoundarybwSxxcx5yC7Zsn2G--
```

### Example Response

```json
file_saved
```

## `DELETE /upload/description/:channel/:auth`

| Paramater | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| image_id | Yes | int | id of the image | 

### Example URL

http://www.hitbox.tv/api/upload/description/test-account/21321321321312?image_id=85926

### Example Response 

```json
success
```

## `POST /upload/team/:username/:auth`

### Example URL

http://www.hitbox.tv/api/upload/team/test-account/12312312

### Example Payload

```
------WebKitFormBoundarytEGA8o2SicDQq1bW
Content-Disposition: form-data; name="file"; filename="hitbox-icon-green.png"
Content-Type: image/png


------WebKitFormBoundarytEGA8o4Sic33431bW--
```

### Example Response 

```json
{
  "logo":{
    "small":"/static/img/teams/logo_54dfce333ee3_small.png",
    "large":"/static/img/teams/logo_54dfce333ee3_large.png"
  },
  "cover":null
}
```
