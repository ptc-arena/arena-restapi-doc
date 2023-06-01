# DELETE Change Affected Item
changes/&lt;GUID&gt;/items/&lt;GUID&gt;

Removes an item with a given GUID from a change with a given GUID.   Items can only be removed from changes in the Open and Unlocked lifecycle phase.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 204<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
