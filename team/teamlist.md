# Team List API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /teamlist](/team/teamlist.md#get-teamlist) | Returns a team list |

## `GET /teamlist`

Returns a team list.

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| q | no | string | Query to seach for |

### Example URL

https://www.hitbox.tv/api/teamlist?q=TheBestTeam

### Example Response 

```json
{
   "teams":[
      {
         "group_id":"1",
         "group_name":"TheBestTeamAround"
      },
      ...
   ]
}
```
