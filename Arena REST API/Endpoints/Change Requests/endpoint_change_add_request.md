# POST Add a Request to a Change
/changes/&lt;GUID&gt;/requests

Adds a Request to a Change. Users must have a Read Change Summary and  Edit Change Requests rule for the Change. Additionally users must have a Read Request Summary rule for the request being added.

The Change must have a lifecycle status of OPEN_AND_UNLOCKED. The Request being added must have a lifecycle status of PROMOTED.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Sample Request Body
Add a Request with a GUID of N5P8R8R73GZYH0J024AP to a Change with a GUID specified in the URL.

```
{
    "request": {
        "guid": "N5P8R8R73GZYH0J024AP"
    }
}
```
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

## Sample Response Body
A request is added to a change. A new change-request associatiion GUID is created.

```
{
    "guid": "J1L4N4N3ZCUI1K3BE6EB",
    "request": {
        "guid": "N5P8R8R73GZYH0J024AP",
        "number": "ECR-000001"
    }
}
```
