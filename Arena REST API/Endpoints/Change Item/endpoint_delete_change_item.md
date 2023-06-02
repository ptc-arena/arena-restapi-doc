# DELETE Change Affected Item
changes/&lt;GUID&gt;/items/&lt;GUID&gt;

Removes an item with a given GUID from a change with a given GUID.   Items can only be removed from changes in the Open and Unlocked lifecycle phase.

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
No JSON response.

Change is not in an editable lifecycle

```
{
   "status":403,
   "errors":[
      {
         "code":3024,
         "message":"Either you do not have privileges to access the requested data or it does not exist."
      }
   ]
}
```
Request with invalid GUID \(item not included in change\)

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
