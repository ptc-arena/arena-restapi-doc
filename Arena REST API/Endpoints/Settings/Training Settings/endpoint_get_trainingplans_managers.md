# GET Training Managers
/settings/trainingplans/managers

Returns all the Training Plan managers of a workspace.

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
Get the Training Plan Managers  of  a workspace.

GET /settings/trainingplans/managers

```
{
    "count": 2,
    "results": [
        {
            "email": "hwalker@everyroadgps.com",
            "fullName": "Heidi Walker",
            "guid": "WEYH0DYPCFWFYH0JSIPD"
        },
        {
            "email": "tmakamuri@everyroadgps.com",
            "fullName": "Toshiro Makamuri",
            "guid": "J1L4N0LCZ2J2L4N6F6ZL"
        }
    ]
}
```
