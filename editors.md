# Editor API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /editors/:channel](/editors.md#get-editorschannel) |  |
| [POST /editors/:channel](/editors.md#get-editorschannel | |

## `GET /editors/:channel`

Returns list of editors for a channel.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

### Example URL

https://www.hitbox.tv/api/editors/test-account

### Example Response 

```json
{
   "list":[
      {
         "user_name":"Another-Test",
         "user_logo":"\/static\/img\/channel\/another-test_52274f9e8159b_large.jpg",
         "user_logo_small":"\/static\/img\/channel\/another-test
         _52274f9e8159b_small.jpg"
      }
      ...
   ]
}
```

## `POST /editors/:channel`

Adds or Removes users from the editor list.

### Example POST Payload

All variables required. Toggle the `remove` boolean as needed.

```json
{
   "user_name":"Hitakashi",
   "authToken":"b2733e8c4f13184465ea4b268f8667f996e3b447",
   "editor":"hitabot",
   "remove":false
}
```

### Example Response

Even on duplicate 
```json
success
```

If user is not found

```json
editor_not_found
```
