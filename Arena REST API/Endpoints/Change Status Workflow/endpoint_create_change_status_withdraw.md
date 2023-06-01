# POST Change Status (Withdraw)
/changes/statuschanges

This endpoint can be used  to change the status of a Change object. Changes that have a status of SUBMITTED_FOR_ROUTING or SUBMITTED_FOR_APPROVAL can be withrawn by inputting a value of OPEN_AND_UNLOCKED for status within the request body.

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
