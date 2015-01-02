# Ingest List API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /ingests/default_list](/ingests/default_list.md#get-ingestsdefault_list) | Returns the list of streaming ingests |

## `GET /ingests/default_list`

### Example URL

https://www.hitbox.tv/api/ingests/default_list

### Example Response 

I've only listed two since it's a big list.

```json
[
   {
      "ingest_location":"Default",
      "ingest_url":"rtmp://live.hitbox.tv/push"
   },
   {
      "ingest_location":"EU-West (Frankfurt)",
      "ingest_url":"rtmp://live.fra.hitbox.tv/push"
   }
]
```
