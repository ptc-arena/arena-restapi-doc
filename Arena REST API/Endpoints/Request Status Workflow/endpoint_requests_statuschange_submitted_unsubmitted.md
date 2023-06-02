# POST Requests Status Change (Submitted to Unsubmitted)
/requests/statuschanges

This example of this endpoint demonstrates how to change the status of a Request from Submitted to Unsubmitted. This endpoint example is equivalent to withdrawing a submitted Request within the browser-based application.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 201  | Success  |
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
