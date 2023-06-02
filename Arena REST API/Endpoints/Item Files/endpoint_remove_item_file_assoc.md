# DELETE Item File Association
/items/&lt;GUID&gt;/files/&lt;GUID&gt;

Removes a File association from an Item with a given GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 204  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
No JSON response.

Produces an error if the requested file association does not exist.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3029,
      "message": "The file association does not exist between object \"Q8SBG6CHGDWDWB7W8EJG\" and object \"EWGZ4U0541K0J2TJSQGG\"."
    }
  ]
}
```
