# POST Change Status (Complete With Implementation Status)


/changes/statuschanges

This endpoint can be used  to change the status of a  object. This version of the POST Change Status endpoint demonstates how to complete a Change while updating its implementation status. Only Change Administators can perform this version of the endpoint. 

For changes that have reached a status of  EFFECTIVE, a Change administrator can complete the Change while updating the implementation status by inputting a status of COMPLETED and inputting a valid value for implementationStatus. Supported values for implementationStatus can be found by executing the GET Change Implementation Statuses endpoint.

In addition to effective changes with permanent effectivity, this endpoint can be used on expired changes with temporary effectivity which are also known as deviations.

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
For Change administrators, inputting a status of COMPLETED and an implementationStatus in an effective Change updates the implementation status to the specified value and updates the Change status to COMPLETED.



POST /changes/statuschanges



```
{
    "change": {
        "guid": "O6Q9S5QH47QTCUAADB0E"
    },
    "comment": "Change completed and impelentation is done.",
    "implementationStatus": {
        "value": "DONE"
    },
    "status": "COMPLETED"
}
```


```
{
    "change": {
        "guid": "O6Q9S5QH47QTCUAADB0E",
        "number": "ECO-000022"
    },
    "comment": "Change completed and impelentation is done.",
    "implementationStatus": {
        "value": "DONE"
    },
    "status": "COMPLETED"
}
```
