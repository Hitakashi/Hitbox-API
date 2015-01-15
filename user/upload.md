# Upload Account Avatar
***

I won't document each and every API payload as they are all similar. I will add each API endpoint to table.

| Endpoint | Description |
| ---- | --------------- |
| [POST /upload/account/:user/:auth](/upload.md#post-uploadaccountuserauth) | Changes a users avatar. |
| [POST /upload/account/:channel/:auth](upload.md#get-uploaddescriptionchannelauth) | Changes channel banners. |
| [GET /upload/description/:channe/:auth](/upload.md#get-uploaddescriptionchannelauth) | Returns images uploaded for profile description use |
| [POST /upload/description/:channel/:auth](upload.md#) | Uploads images for profile description use |

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

## `GET /upload/description/:channel/:auth`

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
