# POST Change Status (Lock/Unlock)
/changes/statuschanges

This endpoint can be used  to change the status of a Change object. This article demonstates how to lock a change to prevent users from editing any of its views. This article also demonstrates how to unlock a change.

To lock a change with a specific GUID, include the new attribute status and input a value of OPEN_AND_LOCKED within the request body.

To unlock a change, input a value of OPEN_AND_UNLOCKED for the attribute status within the request body.

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
Locks a Change. The Change must have an initial status of OPEN_AND_UNLOCKED.

POST /changes/statuschanges

**Request** 

```
{
    "change": {
        "guid": "Q8SBU7SJ69SVEWCEKLBO"
    },
    "comment": "Locking change.",
    "status": "OPEN_AND_LOCKED"
}
```
**Response** 

```
{
    "change": {
        "guid": "Q8SBU7SJ69SVEWCEKLBO",
        "number": "ECO-000020"
    },
    "comment": "Locking change.",
    "status": "OPEN_AND_LOCKED",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/6B52B6D575A269HDKE",
           "app": "https://app.bom.com/6B52B6D575A269HDKE"

   }
}
```
Unlocks a Change. Change must initially have a status of OPEN_AND_LOCKED.

POST /changes/statuschanges

**Request** 

```
{
    "change": {
        "guid": "Q8SBU7SJ69SVEWCEKLBO"
    },
    "comment": "Unlocking Change to edit routing and description.",
    "status": "OPEN_AND_UNLOCKED"
}
```
**Response** 

```
{
    "change": {
        "guid": "Q8SBU7SJ69SVEWCEKLBO",
        "number": "ECO-000020"
    },
    "comment": "Unlocking Change to edit routing and description.",
    "status": "OPEN_AND_UNLOCKED",
    "url": {
           "api": "https://api.arenasolutions.com/v1/changes/62E11329239730KJNM",
           "app": "https://app.bom.com/62E11329239730KJNM"

   }
}
```
