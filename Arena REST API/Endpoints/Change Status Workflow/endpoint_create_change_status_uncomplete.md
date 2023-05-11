# POST Change Status (Unmarking as Complete)


/changes/statuschanges

This endpoint can be used  to change the status of a  object. This version of the POST Change Status endpoint demonstates how to unmark the completion of a completed Change. Only Change Administators can perform this version of the endpoint. 

For changes that have reached a status of  COMPLETED, a Change administrator can remove the COMPLETED status of the change by inputting a value of EFFECTIVE for the attribute status within the request body of the POST Change Status endpoint.

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
