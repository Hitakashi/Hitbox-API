# Upload Account Avatar
***

This API I have no clue have to actually do this via outside methods, so here's the info I have.

| Endpoint | Description |
| ---- | --------------- |
| [POST /upload/account/:user/:auth](/upload/account/index.md#post-uploadaccountuserauth) | Sends a Tweet to a Users linked Twitter account. |

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
