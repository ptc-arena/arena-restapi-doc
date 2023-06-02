# GET Training Manager
/settings/trainingplans/managers/&lt;GUID&gt;

If the GET Training Managers endpoint is  appended with a valid guid, it returns the information of a specific Training Plan Manager.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get a specific Training Plan Manager with a given GUID.

GET /settings/trainingplans/managers/WEYHODYPCFWFYHOJSIPD

```
{
    "email": "hwalker@everyroadgps.com",
    "fullName": "Heidi Walker",
    "guid": "WEYH0DYPCFWFYH0JSIPD"
}
```
