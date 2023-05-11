# POST Change Status (Cancel)


/changes/statuschanges

This endpoint can be used  to change the status of a  object. This version of the POST Change Status endpoint demonstates how to cancel a Change. Only Change Administators can perform this version of the endpoint. 

For changes that have reached a status of OPEN_AND_UNLOCKED or REJECTED, a Change administrator can cancel the change by inputting a value of CANCELED for the attribute status within the request body of the POST Change Status endpoint.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Requests and Responses
For Change administrators, inputting a status of CANCELED in a Change that has a status of OPEN_AND_UNLOCKED or REJECTED cancels the change.



POST /changes/statuschanges



```
{
    "change": {
        "guid": "P7RAT6RI58RUDVBBEC1H"
    },
    "comment": "As discussed in the Monday triage meeting, we are canceling this Change.",
    "status": "CANCELED"
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
    "comment": "As discussed in the Monday triage meeting, we are canceling this Change.",
    "status": "CANCELED"
}
```
