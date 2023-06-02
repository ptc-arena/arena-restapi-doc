# DELETE Remove a Request from a Change
changes/&lt;GUID&gt;/requests/&lt;GUID&gt;

Removes an request with a given GUID from a change with a given GUID.

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

## Sample Responses
* No JSON response.

* Request with invalid GUID (item not included in change)

```
{
   "status":400,
   "errors":[
      {
         "code":3012,
         "message":"The requested object with guid \"UCWFYFYEAN5YH0JSFPEP\" is not found."
      }
   ]
}
```
