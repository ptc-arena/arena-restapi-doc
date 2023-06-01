# DELETE Training Plan Users
/trainingplans/&lt;GUID&gt;/users/&lt;GUID&gt;

Removes a user from a Training Plan.  In order to remove  a user from a Training Plan, the user must be the assigned Training Manager of the Training Plan.

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

Request with invalid GUID

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
