# POST Add a Request to a Change


/changes/&lt;GUID&gt;/requests

Adds a Request to a Change. Users must have a Read Change Summary and  Edit Change Requests rule for the Change. Additionally users must have a Read Request Summary rule for the request being added.

The Change must have a lifecycle status of OPEN_AND_UNLOCKED. The Request being added must have a lifecycle status of PROMOTED.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

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

## Sample Response Body
A request is added to a change. A new change\-request associatiion GUID is created.

```
{
    "guid": "J1L4N4N3ZCUI1K3BE6EB",
    "request": {
        "guid": "N5P8R8R73GZYH0J024AP",
        "number": "ECR-000001"
    }
}
```
