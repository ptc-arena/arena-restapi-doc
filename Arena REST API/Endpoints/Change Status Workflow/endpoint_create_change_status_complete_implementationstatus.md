# POST Change Status (Complete With Implementation Status)


/changes/statuschanges

This endpoint can be used  to change the status of a  object. This version of the POST Change Status endpoint demonstates how to complete a Change while updating its implementation status. Only Change Administators can perform this version of the endpoint. 

For changes that have reached a status of  EFFECTIVE, a Change administrator can complete the Change while updating the implementation status by inputting a status of COMPLETED and inputting a valid value for implementationStatus. Supported values for implementationStatus can be found by executing the GET Change Implementation Statuses endpoint.

In addition to effective changes with permanent effectivity, this endpoint can be used on expired changes with temporary effectivity which are also known as deviations.

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
    "status": "COMPLETED",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/52517F9A48748AVBDC",
           "app": "https://app.bom.com/52517F9A48748AVBDC"

   }
}
```
