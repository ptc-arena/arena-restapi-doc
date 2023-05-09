# POST Change Status (Unmarking as Complete)


/changes/statuschanges

This endpoint can be used  to change the status of a  object. This version of the POST Change Status endpoint demonstates how to unmark the completion of a completed Change. Only Change Administators can perform this version of the endpoint. 

For changes that have reached a status of  COMPLETED, a Change administrator can remove the COMPLETED status of the change by inputting a value of EFFECTIVE for the attribute status within the request body of the POST Change Status endpoint.

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
For Change administrators, inputting a status of EFFECTIVE in a Change that has a status of COMPLETED removes the COMPLETED status of the change.



POST /changes/statuschanges



```
{
    "change": {
        "guid": "O6Q9S5QH47QTCUAADB0E"
    },
    "comment": "Implementation task 7 has not been completed properly. Reopening change to address this..",
    "implementationStatus": {
        "value": "NEEDS_ATTN"
    },
    "status": "EFFECTIVE"
}
```


```
{
    "change": {
        "guid": "O6Q9S5QH47QTCUAADB0E",
        "number": "ECO-000022"
    },
    "comment": "Implementation task 7 has not been completed properly. Reopening change to address this..",
    "implementationStatus": {
        "value": "NEEDS_ATTN"
    },
    "status": "EFFECTIVE"
}
```
