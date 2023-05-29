# POST Change Status (Force Reject)


/changes/statuschanges

This endpoint can be used  to change the status of a  object. This version of the POST Change Status endpoint demonstates how to force reject a Change. Only Change Administators can perform this version of the endpoint. 

For changes that have reached a status of SUBMITTED_FOR_APPROVAL, a Change administrator can force reject the change by inputting a value of REJECTED for the attribute status within the request body of the POST Change Status endpoint.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
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

## Sample Requests and Responses
For Change administrators, inputting a status of REJECTED in a Change that has a status of SUBMITTED_FOR_APPROVAL force rejects the change.



POST /changes/statuschanges



```
{
    "change": {
        "guid": "P7RAT6RI58RUDVBBEC1H"
    },
    "comment": "Per the Executive Escalation meeting, we are unilaterally rejecting the Change.",
    "status": "REJECTED"
}
```


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
