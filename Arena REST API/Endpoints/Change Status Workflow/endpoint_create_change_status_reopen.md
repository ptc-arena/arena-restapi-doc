# POST Change Status (Reopen)
/changes/statuschanges

This endpoint can be used  to change the status of a Change object. This version of the POST Change Status endpoint demonstates how to reopen a rejected Change. Only Change Administators can perform this version of the endpoint. 

For changes that have reached a status of  REJECTED, a Change administrator can reopen the change by inputting a value of OPEN_AND_UNLOCKED for the attribute status within the request body of the POST Change Status endpoint.

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
For Change administrators, inputting a status of OPEN_AND_UNLOCKED in a Change that has a status of REJECTED reopens the change.

POST /changes/statuschanges

**Request** 

```
{
    "change": {
        "guid": "TBVEXAVM9CVYHZFFIG5K"
    },
    "comment": "In light of our new circumstances, we are re-opening the rejected change.",
    "status": "OPEN_AND_UNLOCKED"
}
```
**Response** 

```
{
    "change": {
        "guid": "TBVEXAVM9CVYHZFFIG5K",
        "number": "ECO-000027"
    },
    "comment": "In light of our new circumstances, we are re-opening the rejected change.",
    "status": "OPEN_AND_UNLOCKED",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/16BD9134D5A24BDF9C",
           "app": "https://app.bom.com/16BD9134D5A24BDF9C"

   }
}
```
