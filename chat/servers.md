# Websocket Servers API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /chat/servers](/chat/servers.md#get-chatservers) | Returns chat server addresses |

## `GET /chat/servers`

Returns chat server addresses.

### Example URL

https://www.hitbox.tv/api/chat/servers

### Example Response 

```json
[
   {
      "server_ip":"ec2-54-211-95-56.compute-1.amazonaws.com"
   },
   {
      "server_ip":"ec2-54-221-0-139.compute-1.amazonaws.com"
   },
   {
      "server_ip":"ec2-54-87-101-9.compute-1.amazonaws.com"
   },
   {
      "server_ip":"ec2-54-226-192-118.compute-1.amazonaws.com"
   },
   {
      "server_ip":"ec2-54-162-229-44.compute-1.amazonaws.com"
   }
]
```
