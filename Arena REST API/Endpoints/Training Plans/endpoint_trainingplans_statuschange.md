# POST Training Plans Status Change
/trainingplans/statuschanges

The Training Plan Manager can change the status of   their Training Plan through this endpoint.  Supported statuses: CLOSED and OPEN.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

## Sample Requests and Responses
Upgrade the status of a Training Plan from OPEN to CLOSED.

POST /trainingplans/statuschanges

**Request** 

```
{
    "trainingplan": {
        "guid": "FXH0JWH8VYF0J2L4NZB8"
    },
    "status": "CLOSED",
    "comment": "This initiative is being dropped. Closing Training Plan."
}
```
**Response** 

```
{
    "creationDateTime": "2022-04-25T22:38:35Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "daysToComplete": 30,
    "description": "All employees must review Green 2022 Initiative. Please contact your manager or HR if you have any questions.",
    "guid": "FXH0JWH8VYF0J2L4NZB8",
    "manager": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "name": "EveryHome Green Efficiency Initiative 2022 - North America Line",
    "number": "TRP-000004",
    "status": "CLOSED"
}
```
