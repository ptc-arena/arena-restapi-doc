# POST Change Status (Lock/Unlock)


/changes/statuschanges

This endpoint can be used  to change the status of a  object. This article demonstates how to lock a change to prevent users from editing any of its views. This article also demonstrates how to unlock a change.

To lock a change with a specific GUID, include the new attribute status and input a value of OPEN_AND_LOCKED within the request body.

To unlock a change, input a value of OPEN_AND_UNLOCKED for the attribute status within the request body.

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
Locks a Change. The Change must have an initial status of OPEN_AND_UNLOCKED.



POST /changes/statuschanges



```
{
    "change": {
        "guid": "Q8SBU7SJ69SVEWCEKLBO"
    },
    "comment": "Locking change.",
    "status": "OPEN_AND_LOCKED"
}
```


```
{
    "change": {
        "guid": "Q8SBU7SJ69SVEWCEKLBO",
        "number": "ECO-000020"
    },
    "comment": "Locking change.",
    "status": "OPEN_AND_LOCKED"
}
```
Unlocks a Change. Change must initially have a status of OPEN_AND_LOCKED.



POST /changes/statuschanges



```
{
    "change": {
        "guid": "Q8SBU7SJ69SVEWCEKLBO"
    },
    "comment": "Unlocking Change to edit routing and description.",
    "status": "OPEN_AND_UNLOCKED"
}
```


```
{
    "change": {
        "guid": "Q8SBU7SJ69SVEWCEKLBO",
        "number": "ECO-000020"
    },
    "comment": "Unlocking Change to edit routing and description.",
    "status": "OPEN_AND_UNLOCKED"
}
```
