# POST Change Status (Withdraw)
/changes/statuschanges

This endpoint can be used  to change the status of a Change object. Changes that have a status of SUBMITTED_FOR_ROUTING or SUBMITTED_FOR_APPROVAL can be withrawn by inputting a value of OPEN_AND_UNLOCKED for status within the request body.

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
Inputting a status of OPEN_AND_UNLOCKED to withdraw a submitted Change.

POST /changes/statuschanges

**Request** 

```
{
    "change": {
        "guid": "Q8SBU7SJ69SVEWCCFD2V"
    },
    "comment": "ECO-000024 does not have the required criteria for submission. Withdrawing. Please resubmit once errors are corrected.",
    "status": "OPEN_AND_UNLOCKED"
}
```
**Response** 

```
{
    "change": {
        "guid": "Q8SBU7SJ69SVEWCCFD2V",
        "number": "ECO-000024"
    },
    "comment": "ECO-000024 does not have the required criteria for submission. Withdrawing. Please resubmit once errors are corrected.",
    "status": "OPEN_AND_UNLOCKED",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/AE496C8A7C0E2CSJNB",
           "app": "https://app.bom.com/AE496C8A7C0E2CSJNB"

   }
}
```
