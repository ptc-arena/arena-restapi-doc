# POST Requests Status Change (Submitted to Unsubmitted)
/requests/statuschanges

This example of this endpoint demonstrates how to change the status of a Request from Submitted to Unsubmitted. This endpoint example is equivalent to withdrawing a submitted Request within the browser-based application.

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
Upgrade the status of a Request from SUBMITTED to UNSUBMITTED.

POST /requests/statuschanges

**Request** 

```
{
    "request": {
        "guid": "K2M5O1MD03ML4NJ32ZN1"
    },
    "comment": "From Submitted to Unsubmitted",
    "status": "UNSUBMITTED"
}
```
**Response** 

```
{
    "comment": "From Submitted to Unsubmitted",
    "request": {
        "guid": "K2M5O1MD03ML4NJ32ZN1",
        "number": "ECR-000009"
    },
    "status": "UNSUBMITTED"
}
```
