# Panels API
***

| Endpoint | Description |
| ---- | --------------- |
| [POST /profileenable/:user](/oauth.md#get-oauthaccessuser) | Enable/Disable panel layout. |
| [GET /profile/:user](/profile.md#get-profileuser) | Get panels for user account. |
| [POST /profile/:user](/profile.md#post-profileuser) | Updates panels for user account. |

## `POST /profileenable/:user`

Removes application that has access to your account.

### Example POST Payload

```javascript
{
  "authToken":"SuperSecret",
  "enabled":true,
  "user_name":"test-account"
}
```

### Example Response

Success
```javascript
{
  "success":true
}
```

## `GET /profile/:user`

Returns arrays & objects of panels.

### Example URL

https://www.hitbox.tv/api/profile/test-account

### Example Response

```javascript
{
   "profile":{
      "panels":[
         {
            "id":1,
            "template":"content",
            "headline":"Panel 1",
            "link":"http://google.com",
            "content":"Here's some text!",
            "image":"http://edge.sf.hitbox.tv/static/img/channel/boo-png_553fef3cdd5c1.png"
         },
         {
            "id":2,
            "template":"content",
            "headline":"Panel 2 w/o image",
            "link":"",
            "content":"Super Secret Text!",
            "image":""
         }
      ],
      "sorted":[
         {
            "id":1,
            "template":"content",
            "headline":"Panel 1",
            "link":"http://google.com",
            "content":"Here's some text!",
            "image":"http://edge.sf.hitbox.tv/static/img/channel/boo-png_553fef3cdd5c1.png"
         },
         {
            "id":2,
            "template":"content",
            "headline":"Panel 2 w/o image",
            "link":"",
            "content":"Super Secret Text!",
            "image":""
         }
      ],
      "preview":[

      ]
   }
}
```

## `POST /profile/:user`

Updates panels for user account.

### Example POST Payload

```javascript
{
   "user_name":"test-account",
   "authToken":"SuperSecret",
   "profile":{
      "panels":[
         {
            "id":1,
            "template":"content",
            "headline":"Panel 1",
            "link":"http://google.com",
            "content":"Here's some text!",
            "image":"http://edge.sf.hitbox.tv/static/img/channel/staff-chat-png_553fef3cdd5c1.png"
         },
         {
            "id":2,
            "template":"content",
            "headline":"Panel 2 w/o image",
            "link":"",
            "content":"Super Secret Text!",
            "image":""
         }
      ],
      "sorted":[
         {
            "id":1,
            "template":"content",
            "headline":"Panel 1",
            "link":"http://google.com",
            "content":"Here's some text!",
            "image":"http://edge.sf.hitbox.tv/static/img/channel/staff-chat-png_553fef3cdd5c1.png"
         },
         {
            "id":2,
            "template":"content",
            "headline":"Panel 2 w/o image",
            "link":"",
            "content":"Super Secret Text!",
            "image":""
         }
      ],
      "preview":[

      ]
   }
}
```

### Example Response

```javascript
{
  "error":false
}
```