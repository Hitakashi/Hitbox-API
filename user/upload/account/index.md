# Upload Account Avatar
***

This API I have no clue have to actually do this via outside methods, so here's the info I have. There are other image upload endpoints, but unless there's a need for them I will only document this one.

| Endpoint | Description |
| ---- | --------------- |
| [POST /upload/account/:user/:auth](/user/upload/account/index.md#post-uploadaccountuserauth) | Changes a users avatar. |

## `POST /upload/account/:user/:auth`

Update User Avatar.

### Example URL

https://www.hitbox.tv/api/upload/account/test-account?authToken=123

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
