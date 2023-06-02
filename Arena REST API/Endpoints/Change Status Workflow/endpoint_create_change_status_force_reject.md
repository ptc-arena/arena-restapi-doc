# POST Change Status (Force Reject)
/changes/statuschanges

This endpoint can be used  to change the status of a Change object. This version of the POST Change Status endpoint demonstates how to force reject a Change. Only Change Administators can perform this version of the endpoint. 

For changes that have reached a status of SUBMITTED_FOR_APPROVAL, a Change administrator can force reject the change by inputting a value of REJECTED for the attribute status within the request body of the POST Change Status endpoint.

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
For Change administrators, inputting a status of REJECTED in a Change that has a status of SUBMITTED_FOR_APPROVAL force rejects the change.

POST /changes/statuschanges

**Request** 

```
{
    "change": {
        "guid": "P7RAT6RI58RUDVBBEC1H"
    },
    "comment": "Per the Executive Escalation meeting, we are unilaterally rejecting the Change.",
    "status": "REJECTED"
}
```
**Response** 

```
{
    "administrators": [
        {
            "email": "hwalker@everyroadgps.com",
            "fullName": "Heidi Walker",
            "guid": "WEYH0DYPCFWFYH0JSIPD"
        }
    ],
    "change": {
        "guid": "P7RAT6RI58RUDVBBEC1H",
        "number": "ECO-000023"
    },
    "comment": "Per the Executive Escalation meeting, we are unilaterally rejecting the Change.",
    "status": "REJECTED",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/C11E57AC03C94831BD",
           "app": "https://app.bom.com/C11E57AC03C94831BD"

   }
}
```
