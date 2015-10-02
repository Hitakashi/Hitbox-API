# Editor API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /editors/:channel](/channel/editors.md#get-editorschannel) |  Returns list of editors |
| [GET /editor/:user](/channel/editors.md#get-editoruser) | Returns list of channels a user is a editor in.|
| [POST /editors/:channel](/channel/editors.md#post-editorschannel) | Adds or Removes editors. |

## `GET /editors/:channel`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns list of editor objects that have access to '':channel''.

**Note**: Only the broadcaster of `:channel` can view this API.

### Example URL

https://www.hitbox.tv/api/editors/test-account?authToken=SuperSecret

### Example Response 

```javascript
{
   "list":[
      {
         "user_name":"Another-Test",
         "user_logo":"/static/img/channel/another-test_52274f9e8159b_large.jpg",
         "user_logo_small":"/static/img/channel/another-test_52274f9e8159b_small.jpg"
      }
      ...
   ]
}
```

## `GET /editor/:user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns list of editor objects that `:user` has access to.

### Example URL

https://www.hitbox.tv/api/editor/test-account?authToken=SuperSecret

### Example Response 

```javascript
{
   "list":[
      {
         "user_name":"Another-Test",
         "user_logo":"/static/img/channel/another-test_52274f9e8159b_large.jpg",
         "user_logo_small":"/static/img/channel/another-test_52274f9e8159b_small.jpg"
      }
      ...
   ]
}
```

## `POST /editors/:channel`

Add or Remove Editors for '':channel''

**Note**: Only the broadcaster of '':channel'' can modify this API.

### Example POST Payload

All variables required. Toggle the `remove` boolean as needed.

```javascript
{
   "user_name":"test-account",
   "authToken":"SuperSecret",
   "editor":"test-user",
   "remove":false
}
```

### Example Response

Even on duplicate 
```javascript
{
    "error":false
    "error_msg":"success"
    "success":true
}
```

If user is not found

```javascript
{
    "error":true
    "error_msg":"editor_not_found"
    "success":false
}
```

Failure adding editor

```javascript
{
    "error":true
    "error_msg":"error_adding_editor"
    "success":false
}
```
