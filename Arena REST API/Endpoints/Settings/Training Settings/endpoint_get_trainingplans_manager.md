# GET Training Manager


/settings/trainingplans/managers/&lt;GUID&gt;

If the GET Training Managers endpoint is  appended with a valid guid, it returns the information of a specific Training Plan Manager.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
