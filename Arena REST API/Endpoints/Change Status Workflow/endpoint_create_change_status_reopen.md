# POST Change Status (Reopen)
/changes/statuschanges

This endpoint can be used  to change the status of a Change object. This version of the POST Change Status endpoint demonstates how to reopen a rejected Change. Only Change Administators can perform this version of the endpoint. 

For changes that have reached a status of  REJECTED, a Change administrator can reopen the change by inputting a value of OPEN_AND_UNLOCKED for the attribute status within the request body of the POST Change Status endpoint.

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
